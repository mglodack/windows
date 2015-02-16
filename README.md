# Pretty Sweet Windows Stuff

## Setting Up PowerShell

#### Installing Chocolatey
1. Run the two commands [here](https://chocolatey.org/)
	>The first command is ran in cmd.exe
	>
	>The second is ran in powershell.exe as administrator
#### Installing Necessary Packages
1. Install [Nuget](https://chocolatey.org/packages/NuGet.CommandLine)
	>`choco install nuget.commandline`

2. Install [Ruby](https://chocolatey.org/packages/ruby)
	> `choco install ruby` NOTE: this is ruby v2.15
	
3. Install [git](https://chocolatey.org/packages/git)
	> `choco install git`

#### Modify Powershell environment
1. How to change Powershell permissions (Both are supposed to be valid options)
	>`Set-ExecutionPolicy RemoteSigned`
	
	>`Set-ExecutionPolicy Unrestricted`

2. Better powershell [git environment](https://github.com/dahlbyk/posh-git) (copy and paste this into powershell)

		>(new-object Net.WebClient).DownloadString("http://psget.net/GetPsGet.ps1") | iex install-module posh-git

	Following this you will want to restart your profile by typing `.$PROFILE` (NOTE: if an error occurs cannot find `ssh-agent`then

		>$env:path += ";" + (Get-Item "Env:ProgramFiles(x86)").Value + "\Git\bin"


#### Installing gems for rake
1. Install the necessary gems
	> gem install httparty

TODO: if this gives you an error you should use http try [this](http://stackoverflow.com/questions/19150017/ssl-error-when-installing-rubygems-unable-to-pull-data-from-https-rubygems-o)
		
	>sudo gem sources -r https://rubygems.org
	>sudo gem sources -a http://rubygems.org 

#### Other Powershell help

TODO:
1. Include how to set nuget Local folder (just copy this info from Andrew's README)
