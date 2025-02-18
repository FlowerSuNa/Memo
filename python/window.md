### Window 환경에서 Python 가상환경 활성화에 보안/권한 문제가 발생했을 때

![image](https://github.com/user-attachments/assets/c08c4a33-0407-45b0-8a36-f684704a6781)

- PowerShell에서 유효한 실행 정책 가져오기

```PowerShell
Get-ExecutionPolicy -List
```

> ```output
>         Scope ExecutionPolicy
>         ----- ---------------
> MachinePolicy       Undefined
>    UserPolicy       Undefined
>       Process       Undefined
>   CurrentUser       Undefined
>  LocalMachine       Undefined
> ```

<br>

- PowerShell에서 실행 정책 변경

```PowerShell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

<br>

- PowerShell에서 실행 정책 변경 확인

```PowerShell
Get-ExecutionPolicy -List
```

> ```output
>         Scope ExecutionPolicy
>         ----- ---------------
> MachinePolicy       Undefined
>    UserPolicy       Undefined
>       Process       Undefined
>   CurrentUser    RemoteSigned
>  LocalMachine       Undefined
> ```
