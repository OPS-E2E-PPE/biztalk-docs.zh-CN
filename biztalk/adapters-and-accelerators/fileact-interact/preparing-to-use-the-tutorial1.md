---
title: "准备使用 Tutorial1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4a792b2-8351-4ae8-9d7c-75420c00af03
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efedfeb184b8b0105b8622b6b3f068faffd6a906
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="preparing-to-use-the-tutorial"></a>准备使用本教程
你必须执行以下操作之前使用 A4SWIFT 适配器端到端教程。  
  
1.  对于本教程，你将需要以下 SWIFT 项目：  
  
    -   SWIFT 联盟网关 （压降） 6.1  
  
    -   远程访问 (RA) 6.1  
  
    -   SWIFT WebStation 6.0  
  
    -   SWIFTNet 链接 (SNL) 6.1  
  
2.  你必须配置压降： 压降，在创建 MessagePartners、 终结点和路由规则和测试压降连接，可以在其中安装适配器的计算机。 有关信息，请参阅压降文档。  
  
3.  按照"如何为创建新主机"Microsoft BizTalk Server 帮助中的主题中列出的说明 ([http://go.microsoft.com/fwlink/?LinkId = 100422](http://go.microsoft.com/fwlink/?LinkId=100422)) 若要创建为交互适配器，一个进程内主机名为*interacthost*，，另一个进程内主机对于 FileAct 适配器，名为*fileacthost*。 你将创建为适配器的处理程序时使用这些主机。  
  
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
  
5.  你必须连接到 SWIFT ITB 或实时的环境以进行测试适配器。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk FileAct 和交互适配器端到端教程](../../adapters-and-accelerators/fileact-interact/biztalk-fileact-and-interact-adapters-end-to-end-tutorial.md)   
 [交互实时方案](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md)   
 [交互存储和转发 （推送） 方案](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md)   
 [FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md)   
 [FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md)