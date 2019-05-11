---
title: 准备使用 Tutorial1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4a792b2-8351-4ae8-9d7c-75420c00af03
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8bc4614d82471f6573134c6da47966bf8ca57330
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366576"
---
# <a name="preparing-to-use-the-tutorial"></a>为使用教程做准备
必须执行以下操作之前使用 A4SWIFT 适配器端到端教程。  
  
1.  本教程中，您将需要以下 SWIFT 项目：  
  
    -   SWIFT 联盟网关 （压降） 6.1  
  
    -   远程访问 (RA) 6.1  
  
    -   SWIFT WebStation 6.0  
  
    -   SWIFTNet 链接 (SNL) 6.1  
  
2.  必须配置压降： 压降，在创建 MessagePartners、 终结点和路由规则和测试压降连接，可以在其中安装适配器的计算机。 有关信息，请参阅压降文档。  
  
3.  按照"如何为创建新主机"Microsoft BizTalk Server 帮助中的主题中列出的说明 ([http://go.microsoft.com/fwlink/?LinkId=100422](http://go.microsoft.com/fwlink/?LinkId=100422)) 创建 InterAct 适配器的一个进程内主机名为*interacthost*，另一个进程内主机的名为的 FileAct 适配器*fileacthost*。 创建适配器处理程序时，将使用这些主机。  
  
4.  本教程中创建以下文件夹：  
  
    -   c:\SWIFTAdapterTutorial\Fileact\ClientLocation  
  
    -   c:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime  
  
    -   c:\SWIFTAdapterTutorial\Fileact\ResponseClient  
  
    -   c:\SWIFTAdapterTutorial\Fileact\ResponseServer  
  
    -   c:\SWIFTAdapterTutorial\Fileact\ServerLocation  
  
    -   c:\SWIFTAdapterTutorial\Fileact\StatusEvents  
  
    -   c:\SWIFTAdapterTutorial\Fileact\PullRequest  
  
    -   c:\SWIFTAdapterTutorial\Fileact\PullResponse  
  
    -   c:\SWIFTAdapterTutorial\Interact\HandleRequest  
  
    -   c:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime  
  
    -   c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF  
  
    -   c:\SWIFTAdapterTutorial\Interact\Response  
  
    -   c:\SWIFTAdapterTutorial\Interact\PullRequest  
  
    -   c:\SWIFTAdapterTutorial\Interact\Pullresponse  
  
5.  您必须具有连接到 SWIFT ITB 或实时环境来测试适配器。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk FileAct 和交互适配器端到端教程](../../adapters-and-accelerators/fileact-interact/biztalk-fileact-and-interact-adapters-end-to-end-tutorial.md)   
 [InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md)   
 [InterAct 存储和转发 （推送） 方案](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md)   
 [FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md)   
 [FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md)