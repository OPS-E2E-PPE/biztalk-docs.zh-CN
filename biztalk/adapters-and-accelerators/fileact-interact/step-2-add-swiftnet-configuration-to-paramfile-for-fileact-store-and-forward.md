---
title: "步骤 2： 将 SWIFTNet 配置添加到 FileAct 应用商店应用和向前方案 Paramfile |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 088ab41f-8325-4330-b6f2-0164aa1911b1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b3048198747dd8d283ea9f7b329db27db615436
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-fileact-store-and-forward-scenario"></a>步骤 2： 将 SWIFTNet 配置添加到 Paramfile FileAct 应用商店应用和转发方案
在压降中创建的服务器消息合作伙伴必须指定在 SWIFTNet paramfile 以便接收方可以使用这些值进行初始化。  
  
完成[步骤 1： 配置 FileAct 应用商店应用和转发方案 SWIFT 适配器](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md)在开始此步骤之前。
  
## <a name="add-swiftnet-configuration-to-the-paramfile"></a>将 SWIFTNet 配置添加到 paramfile  
  
1.  在诸如记事本之类的文本编辑器中打开 paramfile。  
  
2.  Paramfile 位于通常： C:\SWIFTAlliance\RA\Ra1\cfg\paramfile  
  
3.  在 paramfile，请突出显示的更改，以指定的服务器消息合作伙伴名称：  
    
     username:snlowner  
  
     subsystem_name:FileactStub  
  
     \#subsystem_group:fileactsnf  
  
     \#subsystem_dependency:Support Swarm  
  
     subsystem_nature： 严重  
  
     subsystem_start:  
  
     **spawn"snlreceiver-SagMessagePartner \<fileact SnF 的服务器 MessagePartnerName >-AdapterMode fileact"**  
  
     * 结束  
  
     subsystem_stop:  
  
     * KILL9:snlreceiver  
  
     * 结束  
  
     subsystem_status:  
  
     * NB:1:snlreceiver  
  
     * 结束  
  
     start_event:SNL001:subsystem FileactStubSnF 已启动  
  
     stop_event:SNL002:subsystem FileactStubSnF 已关闭  
  
     \#subsystem_name:User  
  
     \## subsystem_group:user  
  
     \## subsystem_dependency:  
  
     \#subsystem_nature： 严重  
  
     \#subsystem_start:  
  
     \#* 结束  
  
     \#subsystem_stop:  
  
     \#* 结束  
  
     \#subsystem_status:  
  
     \#* 结束  
  
     #<a name="starteventsnl001subsystem-user-is-up"></a>start_event:SNL001:subsystem 用户已启动  
  
     #<a name="stopeventsnl002subsystem-user-is-down"></a>stop_event:SNL002:subsystem 用户已关闭  
    
  
## <a name="complete-steps"></a>完成步骤
 [FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md)   
 [步骤 1： 配置 SWIFT 适配器 FileAct 应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md)   
 [步骤 3： 创建发送端口和接收端口 FileAct 应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md)   
 [步骤 4： 测试 FileAct 存储区和转发的端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)