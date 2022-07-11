#Depending on the operating system of the host machines(s) that will build or run the containers, the image specified in the FROM statement may need to be changed.
#For more information, please see https://aka.ms/containercompat 

FROM mcr.microsoft.com/windows/servercore:ltsc2019
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell Get-WindowsFeature web-server
RUN powershell Install-windowsfeature web-server
RUN powershell add-windowsfeature web-asp-net45
ARG source
WORKDIR /inetpub/wwwroot
COPY ${source:-obj/Docker/publish} .
