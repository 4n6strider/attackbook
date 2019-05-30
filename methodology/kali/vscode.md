# VS Code

I prefer to use Visual Studio Code.  This allows me to run multiple terminals within vscode and then view output of scans, edit exploit code, edit scripts and commit files to my git repo all within one tool.

{% embed url="https://code.visualstudio.com/Download" %}

## Git Configuration

```bash
#Configure git globals
git config --global user.name "name"
git config --global user.email "email@"
git config --global color.ui true
git config --global core.editor nano

#Generate an SSH key
ssh-keygen -t rsa -b 4096 -C "email@"
​
#copy the pub key to your git provider as an authorized SSH key
cat ./rsa_id.pub

#clone your repo
git clone user@url:/repository-name.git
```

## Manage Extensions

Export extensions from Windows

```text
code --list-extensions > ext.txt
```

Import on Linux

```bash
cat ext.txt | xargs -L 1 code --install-extension --user-data-dir /root/.vscode/
```

### Workspace Template

```javascript
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

