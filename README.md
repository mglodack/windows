# Pretty Sweet Windows Stuff

## Setting Up PowerShell

#### Installing Chocolatey
1. Run the three commands below.  [Steps 1 and 3 can be found here](https://chocolatey.org/)
	
	>` @powershell -NoProfile -ExecutionPolicy unrestricted -Command "iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1'))" && SET PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin`
	
	>`Set-ExecutionPolicy RemoteSigned`
	
	>`iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1'))`

#### Installing Necessary Packages
1. Install [Nuget](https://chocolatey.org/packages/NuGet.CommandLine)
	>`choco install nuget.commandline`

2. Install [Ruby](https://chocolatey.org/packages/ruby)
	> `choco install ruby` NOTE: this is ruby v2.15
	
3. Install [git](https://chocolatey.org/packages/git)
	> `choco install git`

#### Modify Powershell environment
1. Better powershell [git environment](https://github.com/dahlbyk/posh-git) (copy and paste this into powershell)

		>(new-object Net.WebClient).DownloadString("http://psget.net/GetPsGet.ps1") | iex
		>install-module posh-git

	Following this you will want to restart your profile by typing `.$PROFILE` (NOTE: if an error occurs cannot find `ssh-agent`then

		>$env:path += ";" + (Get-Item "Env:ProgramFiles(x86)").Value + "\Git\bin"

	NOTE: This line above may not work if you are running Virtual Machine. In that case run this command
	
		>$env:path += ";" + (Get-Item "Env:ProgramFiles").Value + "\Git\bin"

#### Installing gems for rake
1. Install the necessary gems

	> gem install httparty

TODO: if this gives you an error you should use http try [this](http://stackoverflow.com/questions/19150017/ssl-error-when-installing-rubygems-unable-to-pull-data-from-https-rubygems-o)
		
	>sudo gem sources -r https://rubygems.org
	>sudo gem sources -a http://rubygems.org 

### Local NuGet Feed
If you would like to have NuGet packages that you don't want to share with the world. Then you can simply create a folder at `C:\LocalNuGetFeed` and add it as a Nuget source using the following command:

```nuget sources add -Name Local -Source C:\LocalNuGetFeed\```
