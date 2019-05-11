---
title: 备份 BizTalk Server 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b51e3ae6-08ed-48ca-8977-13f46144a5fa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5f209ea114cb515e0d09f5ddd80bbf864501038
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530616"
---
# <a name="backing-up-biztalk-server-applications"></a>备份 BizTalk Server 应用程序
若要确保可以在硬件故障后恢复 BizTalk Server 系统，务必做好备份。 保留备份的一部分，它是一个不错的主意，若要导出 BizTalk 应用程序到远程服务器，并以备份这些应用程序。  
  
 更高版本，当您还原 BizTalk Server 数据库并重新安装 BizTalk Server，你可以导入这些应用程序。 有关如何导出和导入应用程序的详细信息，请参阅[部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md)。  
  
 对于所有 BizTalk 应用程序的计算机上部署，应导出.msi 文件，并将它们保存在备份位置 （在不同服务器上）。 .Msi 文件，您可以重新安装恢复目标计算机后，BizTalk Server 所需的资源。 应确保这些.msi 文件包括所有所需的资源，并指定要对这些资源的.msi 安装执行的操作。 如果 BizTalk 应用程序依赖于任何用户程序集或.msi 文件中不包含其他 Dll，您必须备份了其单独。  
  
 应用程序导出过程是相同的基于内容的路由方案，以及具有业务流程的方案。 每当更改 BizTalk 应用程序时，您应重复此过程。 有关详细信息，请参阅[如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)。  
  
## <a name="see-also"></a>请参阅  
 [对运行 BizTalk Server 的计算机进行备份](../core/backing-up-a-computer-running-biztalk-server.md)