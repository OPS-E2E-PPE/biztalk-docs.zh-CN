---
title: 如何将程序集安装在 GAC 中 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6afc2f81-fa28-4144-b4bd-21c8f35f2270
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c80e3a5126a56b945b2aa7b53aec71fbe83d678a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971019"
---
# <a name="how-to-install-an-assembly-in-the-gac"></a>如何在 GAC 中安装程序集
手动安装和卸载使用 Gacutil 工具随附的全局程序集缓存 (GAC) 中的 BizTalk 程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
 使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，你可以自动安装到 GAC 中，当从部署的 BizTalk 程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 BizTalk 项目中; 的部署属性中设置此选项请参阅[如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)。 你不能使用此方法将非 BizTalk.NET 程序集安装在 GAC 中;你必须按本主题中所述手动安装它们。  
  
> [!NOTE]
>  也可以在使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台将程序集部署到 BizTalk 应用程序之后，再指定程序集的部署选项。 请参阅[如何修改 BizTalk 程序集的部署选项](../core/how-to-modify-the-deployment-options-of-a-biztalk-assembly.md)，和[如何修改.NET 程序集、 COM 组件、 文件或 BAM 项目的部署选项](../core/modify-deployment-options-of-net-assembly-com-component-file-bam-artifact.md)。  
  
## <a name="prerequisites"></a>先决条件  
使用具有到 GAC 的写入权限的帐户登录。 本地计算机的管理员帐户拥有此权限。  

  
## <a name="install-using-gacutil"></a>使用 gacutil 进行安装
  
1.  将 BizTalk 程序集复制到本地计算机。  
  
2.  打开**Visual Studio 的开发人员命令提示**以管理员身份。  
  
3.  键入以下命令：  
  
     `gacutil /i path_to_assembly_file /f`

    例如，键入：  
    `gacutil /i c:\temp\filename.dll /f`
    
`/f`选项将覆盖任何现有的程序集都具有相同的程序集名称。 有关 gacutil 命令和选项的详细信息，键入`gacutil /?`。 

## <a name="uninstall-using-gacutil"></a>卸载使用 gacutil
卸载程序集从全局程序集缓存 (GAC) 则需要完全取消部署应用程序。 你可以自动执行此过程。 应用到生产环境部署之前，编写预处理脚本中卸载的程序集从 GAC 自动卸载应用程序。 请参阅[前期和后期处理脚本用于自定义应用程序部署](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)。  
  
 脚本还可用于删除其他文件和设置。 请参阅[如何删除其他文件和 BizTalk 应用程序设置](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)。  
 
#### <a name="using-the-windows-interface"></a>使用 Windows 介面  
  
1.  打开到 %systemdrive%\windows\assembly。  
  
2.  右键单击包含你的应用程序，选择在每个程序集文件**卸载**，然后选择**是**以确认。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1.  打开**Visual Studio 的开发人员命令提示**以管理员身份。 
  
2.  键入以下命令：  
  
     `gacutil /u`\<*完全限定程序集名称*\>  
  
     例如，键入：  
     `gacutil /u "hello,Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"`
       
## <a name="see-also"></a>另请参阅  
 [将 BizTalk 程序集从 Visual Studio 部署到 BizTalk 应用程序](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)  
[正在取消部署的 BizTalk 应用程序](../core/undeploying-biztalk-applications.md)   
 [如何卸载 BizTalk 应用程序](../core/how-to-uninstall-a-biztalk-application.md)   
 [如何从 BizTalk 组中删除 BizTalk 应用程序](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md)
 