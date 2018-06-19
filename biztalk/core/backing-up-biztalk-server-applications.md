---
title: 备份 BizTalk 服务器应用程序 |Microsoft 文档
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
ms.openlocfilehash: 1d125a1430aa2d044abba7632fa31a9c89f2bc50
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230373"
---
# <a name="backing-up-biztalk-server-applications"></a>备份 BizTalk Server 应用程序
为确保在硬件故障后可以恢复 BizTalk Server 系统，做好备份至关重要。 作为保留备份的一部分，最好将 BizTalk 应用程序导出到一个远程服务器并加以备份。  
  
 以后，在还原 BizTalk Server 数据库并重新安装 BizTalk Server 时，可以导入这些应用程序。 有关如何导出和导入应用程序的详细信息，请参阅[部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md)。  
  
 对于部署在计算机上的所有 BizTalk 应用程序，应导出 .msi 文件并将其保存在备份位置（在另一台服务器上）。 这些 .msi 文件可用于在恢复目标计算机后重新安装 BizTalk Server 所需的资源。 应当确保这些 .msi 文件中包括所有必需的资源，并确保指定为这些资源而需要对 .msi 安装执行的操作。 如果 BizTalk 应用程序依赖于未包括在 .msi 文件中的任何用户程序集或其他 DLL，则必须对其进行单独备份。  
  
 对于基于内容的路由方案以及具有业务流程的方案，应用程序导出过程相同。 每当更改 BizTalk 应用程序后，都应重复此过程。 有关详细信息，请参阅[how to Export BizTalk 应用程序如何](../core/how-to-export-a-biztalk-application.md)。  
  
## <a name="see-also"></a>另请参阅  
 [备份运行 BizTalk Server 的计算机](../core/backing-up-a-computer-running-biztalk-server.md)