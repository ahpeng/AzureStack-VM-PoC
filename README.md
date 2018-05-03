方便在Azure Global上创建Azure Stack ASDK POC环境。
参考了Yagmurs的模板，并做少量修改，以便支持用Azure Mooncake AAD部署ASDK：
https://github.com/yagmurs/AzureStack-VM-PoC
<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fahpeng%2FAzureStack-VM-PoC%2Fmaster%2Fazuredeploy.json" target="_blank">
    <img src="https://azuredeploy.net/deploybutton.png"/>
</a>

<a href="http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2Fahpeng%2FAzureStack-VM-PoC%2Fmaster%2Fazuredeploy.json" target="_blank">
    <img src="https://raw.githubusercontent.com/shenglol/arm-visualizer/master/src/visualizebutton.png"/>
</a>

该模板可以在Azure Global上创建虚拟机，并自动配置好部署ASDK所需的准备工作。请按照以下步骤执行：
  - 部署模板，Azure区域不妨选择WestUS2
  - VM部署完成后，登录到Azure VM，运行"lusrmgr.msc"设置administrator密码，然后用administrator身份重新登录该VM
  - 运行桌面上的Install-ASDK.ps1

修改的部分包括：
  - 设置AAD账户为username@tenantname.partner.onmschina格式，并修改Azure Stack的部署脚本参数，以支持AzureChinaCloud
  - 支持Windows Server的BYOL，以降低运行成本

可以参考Yagmurs的博客文章：
https://blogs.technet.microsoft.com/yagmurs/deploying-azure-stack-development-kit-asdk-straight-on-azure-vm
