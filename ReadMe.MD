## How to build
```bash
docker build -t ionos-local -f IONSDockerFile .
```

## How to run
```bash
docker run -itd -p 9999:22 -p 10000:5000 -p 10001:8000 -p 10002:80 -v ./notebooks:/workspace ionos-local
```

## How to stop all container
```bash
docker ps -a | awk '{ print $1 }' | grep -v CONTAINER | xargs docker stop
```

## How to delete
```bash
docker ps -a | awk '{ print $1 }' | grep -v CONTAINER | xargs docker rm
```


## How to run fastapi behind uvicorn
```bash
uvicorn main:app --host 0.0.0.0 --port 8000
```

## Customization
```bash
vid@705b619eae1d:~$ find . -name coc-settings.json
./.vim/coc-settings.json
{
  "pyright.enable": true,
  "pyright.inlayHints.variableTypes": false,
  "pyright.inlayHints.parameterTypes": false,
  "pyright.inlayHints.variableTypes": false,
  "pyright.inlayHints.functionReturnTypes": false
}
```

## Things to do in .vimrc in case of issue
```bash
:PlugInstall

:CocInstall coc-pyright
:CocInstall coc-json

:CocConfig
```

## Add fillowing in .profile
```bash
export TERM=xterm-256color
```
