---
title: 步骤 2： 为 FileAct 存储和转发方案 Paramfile 添加 SWIFTNet 配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 088ab41f-8325-4330-b6f2-0164aa1911b1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a287c6063ff60b08a53ec4f05d45da9225f1c30
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998238"
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-fileact-store-and-forward-scenario"></a>步骤 2： 为 FileAct 存储和转发方案 Paramfile 添加 SWIFTNet 配置
在压降中创建的服务器消息合作伙伴必须指定 SWIFTNet paramfile 启用接收方可以使用这些值进行初始化。  
  
完整[步骤 1： 配置 SWIFT 适配器为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md)开始此步骤之前。
  
## <a name="add-swiftnet-configuration-to-the-paramfile"></a>向 paramfile 添加 SWIFTNet 配置  
  
1. 在诸如记事本之类的文本编辑器中打开 paramfile。  
  
2. Paramfile 是通常位于： C:\SWIFTAlliance\RA\Ra1\cfg\paramfile  
  
3. 在 paramfile，请突出显示的更改来指定服务器消息合作伙伴名称：  
    
    username:snlowner  
  
    subsystem_name:FileactStub  
  
    \#subsystem_group:fileactsnf  
  
    \#subsystem_dependency:Support Swarm  
  
    subsystem_nature： 关键  
  
    subsystem_start:  
  
    **生成"snlreceiver-SagMessagePartner \<fileact SnF 的 Server MessagePartnerName\> -AdapterMode fileact"**  
  
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
  
    \#subsystem_nature： 关键  
  
    \#subsystem_start:  
  
    \#* 结束  
  
    \#subsystem_stop:  
  
    \#* 结束  
  
    \#subsystem_status:  
  
    \#* 结束  
  
    # <a name="starteventsnl001subsystem-user-is-up"></a>start_event:SNL001:subsystem 用户已启动  
  
    # <a name="stopeventsnl002subsystem-user-is-down"></a>stop_event:SNL002:subsystem 用户已关闭  
    
  
## <a name="complete-steps"></a>完成的步骤
 [FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md)   
 [步骤 1： 配置 SWIFT 适配器为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md)   
 [步骤 3： 创建发送端口和接收端口为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md)   
 [步骤 4：测试 FileAct 存储和转发端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)