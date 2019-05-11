---
title: VisualStudioHostRestart （应用程序部署示例） |Microsoft Docs
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
ms.openlocfilehash: 96cc470bde0ca8b62a25de81a272d2cf8a891971
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65320827"
---
# <a name="visualstudiohostrestart-application-deployment-sample"></a>VisualStudioHostRestart （应用程序部署示例）
本主题说明如何使用 VisualStudioHostRestart 示例脚本来重新启动主机实例下运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]本地计算机上。 重新部署 Visual Studio 中的程序集，以便 BizTalk Server 运行时立即提取所做的更改时，可以使用此脚本。 或者，可以使用该选项以重新启动主机实例，您可以在项目的部署属性中设置。 有关详细信息，请参阅[如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 此示例脚本按顺序执行以下操作：  
  
1.  在本地计算机上停止所有进程内主机实例。  
  
2.  在本地计算机上启动所有进程内主机实例。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 该示例位于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装文件夹中的，按如下所示：*\<示例路径\>* \Application Deployment\VisualStudioHostRestart。  
  
 示例包括以下文件：  
  
-   RestartBizTalkHostInstances.vbs  
  
## <a name="how-to-use-this-sample"></a>如何使用此示例  
 使用以下过程才能运行此示例。  
  
### <a name="to-run-the-sample"></a>若要运行示例  
  
-   运行 RestartBizTalkHostInstances.vbs。  
  
## <a name="see-also"></a>请参阅  
 [应用程序部署 （BizTalk Server 示例文件夹）](../core/application-deployment-biztalk-server-samples-folder.md)   
 [部署 BizTalk 程序集从 Visual Studio 到 BizTalk 应用程序](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)   
 [部署 BizTalk 应用程序](../core/deploying-biztalk-applications.md)