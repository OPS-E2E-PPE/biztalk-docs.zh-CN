---
title: 如何删除其他文件和 BizTalk 应用程序设置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], deleting settings
- managing [applications], deleting files
- undeploying, settings
- applications, undeploying
- undeploying, files
ms.assetid: b947831a-c988-435c-92ec-45f3fd6967de
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4abf4d2eeff0a06f6f7a121d1a8fbb52b24fdfec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334973"
---
# <a name="how-to-remove-other-files-and-settings-for-a-biztalk-application"></a>如何删除其他文件和 BizTalk 应用程序设置
本主题介绍如何删除的 BizTalk 应用程序时卸载该应用程序可能不会删除的文件和设置 (中所述[如何卸载 BizTalk 应用程序](../core/how-to-uninstall-a-biztalk-application.md))。 例如，证书、 COM 和 COM + 注册表条目以及 COM 文件不会删除除非应用程序包含了一个后处理脚本在卸载时会删除它们。  
  
> [!CAUTION]
>  之前删除任何共享的项，请确保没有其他应用程序在使用它们，或应用程序将无法正常工作。  
  
> [!NOTE]
>  我们建议您通过使用后处理脚本自动化此删除。 有关详细信息，请参阅[使用预处理和后处理脚本自定义应用程序部署到](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)。  
  
- **删除证书。** 有两种方法来从证书存储区中删除证书： 使用证书管理器 (certmgr.exe) 命令行工具或证书管理单元中。 Certmgr.exe 随.NET SDK，这是一个的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装必备组件。 可以手动运行 certmgr.exe 或后续处理脚本从运行它。 有关使用 certmgr.exe 的详细信息，请参阅[证书管理器工具 (certmgr.exe)](http://go.microsoft.com/fwlink/?LinkId=56198)在 Microsoft 网站。  
  
   证书管理单元中包含在 Windows Server 2008 和 Windows Vista。 若要删除证书，请打开管理单元中，如所述在"启动证书管理单元中"帮助中有关你的操作系统，然后删除该证书中所述证书帮助中的"删除证书"。  
  
- **从 Windows 注册表删除程序集。** 若要从 Windows 注册表删除.NET 和 BizTalk 程序集，使用 regsvcs 或 regasm，所含的.NET SDK，这是一个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装必备组件。 有关参考信息，请参阅[.NET 服务安装工具 (Regsvcs.exe)](http://go.microsoft.com/fwlink/?LinkId=56199)并[程序集注册工具 (Regasm.exe)](http://go.microsoft.com/fwlink/?LinkId=56200)在 Microsoft 网站。  
  
- **从 Windows 注册表删除 COM 组件。** 若要从 Windows 注册表删除 COM 组件，请使用 regsvr32。 有关参考信息，请参阅适用于操作系统的帮助中的"Regsvr32"。 此工具包含在 Windows Server 2008 和 Windows Vista Professional 中。  
  
- **从全局程序集缓存 (GAC) 卸载程序集。** 程序集不会自动从 GAC 卸载。 手动或使用脚本，可以从 GAC 卸载程序集。 有关详细信息，请参阅[如何从 GAC 卸载程序集](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4)。  
  
## <a name="prerequisites"></a>先决条件  
 若要删除的文件和本主题中所述的设置，您必须拥有写入权限的 Windows 注册表、 GAC 或证书存储，具体取决于你想要删除的身份登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="see-also"></a>请参阅  
 [正在取消部署 BizTalk 应用程序](../core/undeploying-biztalk-applications.md)   
 [如何卸载 BizTalk 应用程序](../core/how-to-uninstall-a-biztalk-application.md)