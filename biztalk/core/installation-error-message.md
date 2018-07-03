---
title: 安装错误消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installation, error message
- error messages, installation
ms.assetid: 593b033f-03da-43ae-a948-f87aa5e4bccd
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1fe3b422c860b4b697b259dc731f5484fac87455
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001806"
---
# <a name="installation-error-message"></a>安装错误消息
安装适用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器后，为其定义发送或接收位置可能会导致以下错误：  
  
 消息引擎未能添加接收 URL"\<发送/接收位置 URL\>"到"TIBCO EMS"适配器。 原因:"文件或程序集名称 TIBCO。EMS 或其某个依赖项，未找到。"  
  
## <a name="possible-causes"></a>可能的原因  
 此错误通常由下列原因之一引起。  
  
### <a name="assembly-not-in-gac"></a>程序集不在 GAC 中  
 适用于 TIBCO EMS 的 BizTalk 适配器是一个 .NET Framework 应用程序，并使用 .NET Framework 程序集 TIBCO.EMS。 该程序集必须位于 .NET Framework 全局程序集缓存 (GAC) 中，以便 .NET Framework 在运行时查找。  
  
#### <a name="solution"></a>解决方案  
 要确定该程序集是否位于 GAC 中，请打开命令提示符窗口，并键入以下命令：  
  
 `GACUTIL /L TIBCO.EMS`  
  
 如果结果未显示任何项，则必须向 GAC 添加该程序集。 要执行此操作，请打开命令提示符窗口，将目录更改为 TIBCO EMS 安装 clients\cs 目录（默认安装位置为 C:\TIBCO\EMS\Clients\CS），然后运行以下命令：  
  
 `GACUTIL /i TIBCO.EMS.DLL`  
  
### <a name="different-version-of-assembly-in-gac"></a>GAC 中的程序集版本不同  
 TIBCO.EMS.dll 程序集位于 GAC 中，但其版本与构建 TIBCO EMS 的 BizTalk 适配器所使用版本不同。 如果计算机上安装的 TIBCO.EMS.dll 产品版本为 4.2 或更高版本，则应与构建适配器所使用的版本兼容（您可以通过 TIBCO 验证此信息）。  
  
#### <a name="solution"></a>解决方案  
 .NET Framework 提供了解决此问题的方法， 它称为*绑定重定向*，它使用配置文件。  
  
 请遵循以下步骤以消除此错误消息：  
  
1. 使用任意文本编辑器打开 BTSNTSVC.exe.config 文件。  
  
    该文件位于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 目录中（默认安装位置为：[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]）。  
  
2. 将以下条目添加到 BTSNTSVC.exe.config 文件中，为的子\<assemblyBinding\>元素：  
  
```  
<dependentAssembly>  
    <assemblyIdentity name='TIBCO.EMS'  
        publicKeyToken='5b83db8ff05c64ba ' culture='neutral' />  
    <bindingRedirect oldVersion='1.0.0.0-65535.65535.65535.65535'  
        newVersion='1.0.0.0' />  
</dependentAssembly>  
```  
  
 如果先前已修改 BTSNTSVC.exe.config 文件， \<assemblyBinding\>元素不应如下所示：  
  
```  
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
    <probing privatePath="BizTalk Assemblies;Developer  
        Tools;Tracking;Tracking\interop" />  
    <dependentAssembly>  
        <assemblyIdentity name='TIBCO.EMS'  
            publicKeyToken='5b83db8ff05c64ba ' culture='neutral' />  
        <bindingRedirect oldVersion='1.0.0.0-65535.65535.65535.65535'  
            newVersion='1.0.0.0' />  
    </dependentAssembly>  
</assemblyBinding>  
```  
  
1. 在命令提示符下键入命令： `GACUTIL /L TIBCO.EMS`。  
  
2. 复制输出中的 TIBCO.EMS 程序集版本号。  
  
   > [!CAUTION]
   >  显示两个版本号： 一个是 gacutil 实用工具的版本号。 所需的第二个的版本号，之后将显示**版本 =**。  
  
3. 之后粘贴之间引号中，BTSNTSVC.exe.config 文件中的版本号**newVersion =** （以粗体显示上一 XML 示例中的字符）。  
  
4. 保存修改后的 BTSNTSVC.exe.config 文件。  
  
5. 重新启动 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 主机。  
  
## <a name="see-also"></a>请参阅  
 [TIBCO Enterprise Message Service 的疑难解答](../core/troubleshooting-tibco-enterprise-message-service.md)