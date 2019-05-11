---
title: 如何恢复 BizTalk Server 配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1d39e50-4296-49c7-bd1e-63b1325af168
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59910e1af14ff9d21ea196d9ec92202772541876
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335490"
---
# <a name="how-to-recover-the-biztalk-server-configuration"></a>如何恢复 BizTalk Server 配置
作为恢复 BizTalk server 的一部分，您还必须导入安装 BizTalk Server 时所创建的配置文件。  
  
## <a name="prerequisites"></a>先决条件  
 您必须为要执行此过程的管理员组的成员身份登录。  
  
### <a name="to-recover-the-biztalk-server-configuration"></a>若要恢复 BizTalk Server 配置  
  
1. 使用记事本，编辑您以前备份的 BizTalk Server 配置文件，并输入用户帐户密码的所有 BizTalk Server 服务。  
  
2. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 配置**。  
  
3. 在中**Microsoft BizTalk Server 配置**，单击**导入配置**。  
  
    验证出现任何功能的前面没有失效图标。 如果有配置错误的任何功能，现在是时候更正它们。  
  
4. 单击**应用配置**。  
  
    别忘了 BizTalk Server 的已配置的功能，请关闭配置窗口。  
  
## <a name="see-also"></a>请参阅  
 [恢复运行 BizTalk Server 的计算机](../core/recovering-a-computer-running-biztalk-server.md)   
 [如何备份 BizTalk Server 配置](../core/how-to-back-up-the-biztalk-server-configuration.md)