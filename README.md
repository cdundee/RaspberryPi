# RaspberryPi
Install .NET Core to RaspberryPi

Download Linux ARM 32-bit SDK as well as the ASP.NET Runtime so those are packages available for any web apps you make.
Link to download (.NET Core 3.1): https://dotnet.microsoft.com/download/dotnet-core/3.1

**First run**
```
sudo apt-get install curl libunwind8 gettext
```

**Download .NET Core**
```
wget https://download.visualstudio.microsoft.com/download/pr/8ccacf09-e5eb-481b-a407-2398b08ac6ac/1cef921566cb9d1ca8c742c9c26a521c/aspnetcore-runtime-3.1.2-linux-arm.tar.gz
wget https://download.visualstudio.microsoft.com/download/pr/30ed47bb-c25b-431c-9cfd-7b942b07314f/5c92af345a5475ca58b6878dd974e1dc/dotnet-runtime-3.1.2-linux-arm.tar.gz
wget https://download.visualstudio.microsoft.com/download/pr/21a124fd-5bb7-403f-bdd2-489f9d21d695/b58fa90d19a5a5124d21dea94422868c/dotnet-sdk-3.1.200-linux-arm.tar.gz
```

**Run (first time only)**
```
mkdir -p $HOME/dotnet && tar zxf dotnet-runtime-3.1.2-linux-arm.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet 
export PATH=$PATH:$HOME/dotnet
```

**Run to extraxt tar**
```
tar zxf aspnetcore-runtime-3.1.2-linux-arm.tar.gz -C $HOME/dotnet
```

**Run to extraxt tar**
```
tar zxf dotnet-sdk-3.1.200-linux-arm.tar.gz -C $HOME/dotnet
```

**Check installation**
```
dotnet --info
```

## Publish your project to the Pi

```
dotnet publish -r linux-arm
cd bin\Debug\netcore3.1\linux-arm\publish
scp -r . pi@xxx.xxx.xxx.xxx:/home/pi/Desktop/pitest
```

_xxx.xxx.xxx.xxx is the ip of your Pi_

`From the Pi, I'll need to "sudo chmod +x" the pitest application to make sure it is executable.`


