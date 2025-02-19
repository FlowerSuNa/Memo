## 리소스 모니터링

- RAM

  ```bash
  watch -n 10 free -h
  ```

- GPU

  ```bash
  watch -n 10 nvidia-smi
  ```

- Disk
  
  ```bash
  du -h --max-depth=1 / | sort -hr
  ```
