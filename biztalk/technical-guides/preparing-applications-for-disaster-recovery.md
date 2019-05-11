---
title: 准备灾难恢复应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0ef93099-aa6b-424a-a4ce-87d855c6afe3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b9d328d8c1e2f8085c8a1a1709a78824661f62c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379455"
---
# <a name="preparing-applications-for-disaster-recovery"></a>准备灾难恢复应用程序
（二进制文件和配置项目如接收位置和发送端口） 的 BizTalk 应用程序部署到生产 BizTalk 组时在灾难恢复站点还原组。 此配置可能需要进行的更改取决于是否有配置位置，如接收位置和发送端口是特定于生产的。  
  
 若要在灾难恢复站点，加快应用程序的还原操作[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装二进制文件的.msi 文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时服务器必须保持最新的灾难恢复[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行服务器。 灾难恢复特定的应用程序配置.msi 文件在灾难恢复站点还原生产 BizTalk 组时，可能需要安装才能配置，灾难恢复特定于项目的应用程序，例如接收位置和发送端口，根据需要。  
  
## <a name="see-also"></a>请参阅  
 [部署应用程序](../technical-guides/deploying-an-application.md)