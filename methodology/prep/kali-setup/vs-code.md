# VS Code

I prefer to use Visual Studio Code.  This allows me to run multiple terminals within vscode and then view output of scans, edit exploit code and commit files to my git repo all within one tool.

{% embed url="https://code.visualstudio.com/Download" %}

{% hint style="info" %}
You can export your list of installed vscode extensions and install them using the command line.
{% endhint %}

Export extensions from Windows

```text
code --list-extensions > ext.txt
```

Import on Linux

```bash
cat ext.txt | xargs -L 1 code --install-extension --user-data-dir /root/.vscode/
```

### Workspace Template

```text
{
	"folders": [
		{
			"path": "."
		}
	],
	"extensions": {
		"recommendations": [
			"CoenraadS.bracket-pair-colorizer",
			"DavidAnson.vscode-markdownlint",
			"daylerees.rainglow",
			"christian-kohler.path-intellisense",
			"formulahendry.code-runner",
			"humao.rest-client",
			"infosec-intern.snort",
			"ms-python.python",
			"ms-vscode.cpptools",
			"ms-vscode.csharp",
			"ms-vscode.Go",
			"ms-vscode.powershell",
			"msjsdiag.debugger-for-chrome",
			"shakram02.bash-beautify",
			"slevesque.vscode-hexdump",
			"vscode-icons-team.vscode-icons",
			"yzhang.markdown-all-in-one",
			"rebornix.ruby"
		]
	}
}
```

