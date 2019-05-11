---
title: 如何还原应用程序和启用处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83144965-a51a-481a-afd6-7f573b69badb
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4c73d3ac6d96b1cfae4a8e8092669b6b0edcad0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400298"
---
# <a name="how-to-restore-applications-and-enable-processing"></a>如何还原应用程序和启用处理
在 BizTalk 组中配置的应用程序并启用主题所述的步骤操作后的应用程序处理[如何更新运行时计算机](../technical-guides/how-to-update-the-runtime-computers.md)。  
  
### <a name="to-enable-application-configuration-and-restore-application-processing"></a>若要启用应用程序配置和还原应用程序处理  
  
1. 运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组中每个 BizTalk 服务器上的应用程序安装 MSI 文件。  
  
2. 运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组来配置应用程序的灾难恢复站点中的一台服务器上的应用程序配置 MSI 文件。 名称为接收位置和发送端口将保持不变。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序配置 MSI 文件将更新绑定，以便这些项目指向灾难恢复环境中的正确位置。  
  
   > [!NOTE]  
   >  如果接收位置和发送端口不会受到影响的生产站点丢失，可能不需要重新配置灾难恢复特定于位置的应用程序。  
  
3. 还原应用程序处理所有的应用程序，从而接收位置、 发送端口和主机实例。  
  
## <a name="see-also"></a>请参阅  
 [恢复运行时计算机](../technical-guides/recovering-the-runtime-computers.md)