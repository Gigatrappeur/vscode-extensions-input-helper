# input-helper README

Add helpers function for launch.json and tasks.json

## Features

Features:
* [extension.input-helper.hostname](#hostname): return the hostname (the fully hostname and not the short name in %COMPUTERNAME% truncated to 15 chars)

### extension.input-helper.hostname



Example in launch.json
```json
{
    "version": "0.2.0",
    "configurations": [
         {
            "name": "Test",
            "type": "debugpy",
            "request": "launch",
            "module": "uvicorn",
            "cwd": "${workspaceFolder}",
            "args": [
                "main:app",
                "--reload"
            ],
            "env": {
                "HOSTNAME": "${input:get_hostname}",
            }
         }
    ],
    "inputs": [
        {
            "id": "get_hostname",
            "type": "command",
            "command": "extension.input-helper.hostname"
        }
    ]
}
```
