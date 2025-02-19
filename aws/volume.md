## AWS 콘솔에서 Volume 증설 후, 서버 작업

① EBS 볼륨 확인

```bash
lsblk
```

> <출력예시>
> ```output
> NAME    MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
> xvda    259:0    0  100G  0 disk
> └─xvda1 259:1    0   30G  0 part /
> ```

② 파티션 크기 확장 및 확장된 파티션 확인

```bash
sudo growpart /dev/xvda 1
lsblk
```

③ 파일 시스템 유형 확인

```bash
df -Th
```

> <출력예시>
> ```output
> Filesystem     Type   Size  Used Avail Use% Mounted on
> /dev/xvda1     ext4    30G   5G   25G  20% /
> ```

④-1. ext4 파일 시스템인 경우

```bash
sudo resize2fs /dev/xvda1
```

④-2. xfs 파일 시스템인 경우

```bash
sudo xfs_growfs -d /
```

⑤ 정상 반영 확인

```bash
df -h
```

> <출력예시>
> ```output
> Filesystem     Size  Used Avail Use% Mounted on
> /dev/xvda1    100G   5G   95G  5% /
> ```
