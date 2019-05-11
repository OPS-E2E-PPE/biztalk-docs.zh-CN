---
title: 如何备份 BizTalk Server 配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14f89050-c204-4d44-a875-299e690489ef
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9da0d382752a7f3469a8f10a3f2550b06fe84bcb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342658"
---
# <a name="how-to-back-up-the-biztalk-server-configuration"></a>如何备份 BizTalk Server 配置
作为备份的一部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，应该备份与运行的计算机关联的配置设置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 拥有一份原始配置文件，极大地简化还原过程，如果有需要替换的计算机的硬件故障。  
  
 运行每个计算机的配置设置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]存储在 BizTalk Server 配置管理器创建的 XML 文件。 每当您更改的 BizTalk 服务器，配置应导出到备份位置更新的配置文件。 这有助于确保在配置文件可用，如果必须替换 BizTalk server。  
  
## <a name="prerequisites"></a>先决条件  
 您必须为要执行此过程的 BizTalk Server Administrators 组的成员身份登录。  
  
### <a name="to-back-up-the-biztalk-server-configuration"></a>若要备份 BizTalk Server 配置  
  
1.  单击**启动**，单击**所有程序**，单击**Microsoft BizTalk Server**，然后单击**BizTalk Server 配置**。  
  
2.  在中**Microsoft BizTalk Server 配置**，单击**导出配置**。  
  
3.  在中**另存为**对话框中，浏览到存储备份的位置。  
  
4.  在中**文件名**框中，键入配置文件的名称，然后单击**保存**。  
  
## <a name="see-also"></a>请参阅  
 [备份运行 BizTalk Server 的计算机](../core/backing-up-a-computer-running-biztalk-server.md)   
 [如何恢复 BizTalk Server 配置](../core/how-to-recover-the-biztalk-server-configuration.md)