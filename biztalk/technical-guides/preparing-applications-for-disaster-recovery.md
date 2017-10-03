---
title: "准备应用程序的灾难恢复 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0ef93099-aa6b-424a-a4ce-87d855c6afe3
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7028b1386f71f653dfc41b9de2522cdbd8d02126
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="preparing-applications-for-disaster-recovery"></a>准备应用程序的灾难恢复
在组还原在灾难恢复站点时，BizTalk 应用程序 （二进制文件和配置项目如接收位置和发送端口） 将部署到生产 BizTalk 组。 此配置可能需要更改取决于是否有配置位置，例如接收位置和发送生产特定的端口。  
  
 若要在灾难恢复站点上，加快应用程序还原[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装二进制文件的.msi 文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时服务器必须保持最新的灾难恢复[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时服务器。 灾难恢复特定应用程序配置.msi 文件在灾难恢复站点还原生产 BizTalk 组时，可能需要安装才能配置，灾难特定于恢复的项目的应用程序，例如接收位置并根据需要发送端口。  
  
## <a name="see-also"></a>另请参阅  
 [部署应用程序](../technical-guides/deploying-an-application.md)