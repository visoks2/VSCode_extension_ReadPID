Reads program PID on debug (when attaching)
add to settings.json:

``` "ReadPid.AppName" : "your app name", ```

to launch.json:
```
{ 
	"name": "(gdb) Attach",
	"type": "cppdbg",
	"request": "attach",
	"program": "${workspaceFolder}/yourexe",
	"processId": "${command:ReadPid}",
	"MIMode": "gdb",
	"setupCommands": [
		{
			"description": "Enable pretty-printing for gdb",
			"text": "-enable-pretty-printing",
			"ignoreFailures": true
		}
	]
}
```

