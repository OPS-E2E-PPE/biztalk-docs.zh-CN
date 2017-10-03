---
title: "如何删除其他文件和 BizTalk 应用程序设置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [applications], deleting settings
- managing [applications], deleting files
- undeploying, settings
- applications, undeploying
- undeploying, files
ms.assetid: b947831a-c988-435c-92ec-45f3fd6967de
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9ad98e0f0fc1e65281a1d8195be4f4a708d004f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-other-files-and-settings-for-a-biztalk-application"></a>如何删除 BizTalk 应用程序的其他文件和设置
本主题描述如何删除在卸载应用程序时不能删除 BizTalk 应用程序的文件和设置 (中所述[如何卸载 BizTalk 应用程序](../core/how-to-uninstall-a-biztalk-application.md))。 例如，证书、COM 和 COM+ 注册表条目以及 COM 文件就不会删除，除非该应用程序包括在卸载时会删除它们的后处理脚本。  
  
> [!CAUTION]
>  在删除任何共享项之前，请确保没有其他应用程序在使用它们，否则应用程序将不会正常工作。  
  
> [!NOTE]
>  我们建议您通过使用后处理脚本，令这一删除自动化。 有关详细信息，请参阅[使用自定义应用程序部署到的前期和后期处理脚本](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)。  
  
-   **删除证书。** 可通过两种方式从证书存储中删除证书：使用证书管理器 (certmgr.exe) 命令行工具或证书管理单元。 Certmgr.exe 安装使用.NET SDK，这是一个的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装系统必备组件。 您可以手动运行 certmgr.exe，也可以通过后处理脚本自动运行该文件。 有关使用 certmgr.exe 的详细信息，请参阅[证书管理器工具 (certmgr.exe)](http://go.microsoft.com/fwlink/?LinkId=56198)在 Microsoft Web 站点。  
  
     Windows Server 2008 和 Windows Vista 中均包括证书管理单元。 若要删除某一证书，请根据操作系统帮助文件中“启动证书管理单元”的说明打开该管理单元，然后根据证书帮助中“删除证书”的说明删除该证书。  
  
-   **从 Windows 注册表中移除程序集。** 若要从 Windows 注册表中删除 .NET 和 BizTalk 程序集，请使用 .NET SDK 所附带的 regsvcs 或 regasm，.NET SDK 是 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装的先决条件之一。 有关引用信息，请参阅[.NET 服务安装工具 (Regsvcs.exe)](http://go.microsoft.com/fwlink/?LinkId=56199)和[程序集注册工具 (Regasm.exe)](http://go.microsoft.com/fwlink/?LinkId=56200)在 Microsoft Web 站点。  
  
-   **从 Windows 注册表中删除 COM 组件。** 若要从 Windows 注册表删除 COM 组件，请使用 regsvr32。 有关参考信息，请参阅操作系统帮助中的“Regsvr32”。 Windows Server 2008 和 Windows Vista Professional 中均包括此工具。  
  
-   **从全局程序集缓存 (GAC) 中卸载程序集。** 程序集不从 GAC 中自动卸载。 您可以从 GAC 手动卸载程序集，或者使用脚本进行卸载。 有关详细信息，请参阅[如何从 GAC 中卸载程序集](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4)。  
  
## <a name="prerequisites"></a>先决条件  
 若要删除本主题中描述的文件和设置，则根据您要删除的内容，您登录时所采用的身份必须对 Windows 注册表、GAC 或证书存储具有写权限。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="see-also"></a>另请参阅  
 [正在取消部署的 BizTalk 应用程序](../core/undeploying-biztalk-applications.md)   
 [如何卸载 BizTalk 应用程序](../core/how-to-uninstall-a-biztalk-application.md)