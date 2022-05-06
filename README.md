# Anyconnect Umbrella Configuration MSI Installer
WXS file to build a MSI file that installs configuration files for Anyconnect Roaming Security Module (Umbrella)

Tested Environment
- Windows 10 21H1 (64 Bit)
- Umbrella Root Certificate deployed in Mozilla Firefox Certificate Store v100.0 and Certificate Manager's Trusted Root Certificate Authorities


This WXS file creates an MSI file that installs and deploys:
- Umbrella Module Profile - OrgInfo.json
- Umbrella Root CA - Cisco_Umbrella_Root_CA.cer


This does **not** deploy Anyconnect Core VPN or Anyconnect Umbrella Roaming Security Module. These can be deployed using MSI files found on software.cisco.com


Prerequisites:
- Wix Toolset 3.11.2 (https://wixtoolset.org/releases/)
- Wix Toolset Visual Studio 2022 Extension
- Visual Studio 2022 Enterprise (https://visualstudio.microsoft.com/vs/)

Usage
1. Download the Module Profile and the latest Umbrella Root CA file from dashboard.umbrella.com
2. Download the provided WXS file
3. Create a *Setup Project for Wix v3* in Visual Studio 2022 with name *CiscoUmbrellaConfiguration*
4. Overwrite the *Product.wxs* template with the provided *Product.wxs*
5. Suppress ICE Validation in Visual Studio 2022
6. Add the *WixIisExtension.dll* as a reference to the project
7. Place *Cisco_Umbrella_Root_CA.cer* and *OrgInfo.json* into _%User%\source\repos\CiscoUmbrellaConfiguration\CiscoUmbrellaConfiguration\bin\Debug\_
8. Build the MSI
9. Deploy the MSI installer as needed

Youtube Tutorial (7 minutes): https://youtu.be/QU54ZZirQSI

