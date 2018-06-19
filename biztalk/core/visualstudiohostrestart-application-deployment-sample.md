---
title: VisualStudioHostRestart （应用程序部署示例） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0b82627-1552-479d-a083-cdc9fe4843c3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d98a3a5e497a4476de897c8008f3a9976812209a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974099"
---
# <a name="visualstudiohostrestart-application-deployment-sample"></a>VisualStudioHostRestart（应用程序部署示例）
本主题解释如何使用 VisualStudioHostRestart 示例脚本在本地计算机上重新启动在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 下运行的主机实例。 在 Visual Studio 中重新部署程序集时可以使用该脚本，以便 BizTalk Server 运行时能够立即应用更改。 另外，可以使用选项以重新启动主机实例，该选项可以在项目的部署属性中进行设置。 有关详细信息，请参阅[如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例脚本按顺序执行以下操作：  
  
1.  停止本地计算机上的所有进程内主机实例。  
  
2.  启动本地计算机上的所有进程内主机实例。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 示例位于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装文件夹，，如下所示： *\<示例路径\>* \Application Deployment\VisualStudioHostRestart。  
  
 示例包括以下文件：  
  
-   RestartBizTalkHostInstances.vbs  
  
## <a name="how-to-use-this-sample"></a>如何使用本示例  
 请使用以下过程运行本示例。  
  
### <a name="to-run-the-sample"></a>运行示例  
  
-   运行 RestartBizTalkHostInstances.vbs。  
  
## <a name="see-also"></a>另请参阅  
 [应用程序部署 （BizTalk Server 示例文件夹中）](../core/application-deployment-biztalk-server-samples-folder.md)   
 [部署到 BizTalk 应用程序从 Visual Studio BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)   
 [部署 BizTalk 应用程序](../core/deploying-biztalk-applications.md)