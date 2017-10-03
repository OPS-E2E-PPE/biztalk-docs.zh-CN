---
title: "批处理的 SQL 适配器上设置轮询间隔接收位置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- polling interval [receive adapters]
- SQL adapters, polling interval
- receive locations, polling interval
- SQL adapters, receive locations
- receive locations, SQL adapters
ms.assetid: 9053b20d-145a-4445-b414-c0482cf975a0
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 830cafc89c87ce84048bad8f6e4e9f2feb34f565
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="setting-the-polling-interval-on-the-batching-sql-adapter-receive-location"></a>批处理的 SQL 适配器上设置轮询间隔接收位置
你可以设置轮询间隔在批处理 SQL 适配器接收位置 (**BatchControlMessageRecvLoc**) 在开发和生产计算机上以不同的方式。 在开发服务器上，Microsoft 建议您将轮询间隔保留为默认值 30 秒，以便为协议快速激活批处理业务流程。 但是，在生产服务器上，设置为 30 秒可能会影响性能。 激活批之后，可能需要将轮询间隔设置为更高的值，比如五分钟。  
  
 方有关的详细信息，请参阅[管理方](../core/managing-parties.md)。  
  
## <a name="prerequisites"></a>先决条件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="to-set-the-polling-interval-on-the-batching-sql-adapter-receive-location"></a>对批处理 SQL 适配器接收位置设置轮询间隔  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**BizTalk EDI 应用程序**，然后单击**接收位置**。 右键单击**BatchControlMessageRecvLoc**，然后单击**属性**。  
  
2.  在**接收位置属性**对话框中，在**传输**部分中，单击**配置**。  
  
3.  在**SQL 传输属性**对话框框中，更改的值**轮询间隔**从默认值为"30"到所需的值。 针对生产服务器的建议值为“30”。  
  
4.  更改的值**轮询度量单位**的默认值从**秒**到**分钟**。  
  
5.  单击**确定**，然后单击**确定**再次  
  
## <a name="see-also"></a>另请参阅  
 [管理 EDI 和 AS2 解决方案](../core/managing-edi-and-as2-solutions.md)