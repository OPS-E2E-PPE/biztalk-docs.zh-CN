---
title: 步骤 2： 向为 Paramfile 添加 SWIFTNet 配置 InterAct 实时方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a900a6e-3e08-430a-8766-4a7192adba5e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d36758716fb368760e9a93909f70bf4d92c5f840
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992446"
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-interact-real-time-scenario"></a>步骤 2： 向为 Paramfile 添加 SWIFTNet 配置 InterAct 实时方案
在压降中创建的服务器消息合作伙伴必须指定 SWIFTNet paramfile 启用接收方可以使用这些值进行初始化。 在开始此过程之前，必须完成中的说明[步骤 1： 为交互实时方案配置 SWIFT 适配器](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md)。  
  
### <a name="to-add-swiftnet-configuration-to-the-paramfile"></a>若要向 paramfile 添加 SWIFTNet 配置  
  
1. 在诸如记事本之类的文本编辑器中打开 paramfile。  
  
    Paramfile 是通常位于： C:\SWIFTAlliance\RA\Ra1\cfg\paramfile  
  
2. 在 paramfile，请突出显示的更改来指定服务器消息合作伙伴名称：  
  
    username:snlowner  
  
    subsystem_name:InteractStub  
  
    \#subsystem_group:InteractRT  
  
    \#subsystem_dependency:Support Swarm  
  
    subsystem_nature： 关键  
  
    subsystem_start:  
  
    **生成"snlreceiver-SagMessagePartner \<Interact RT 的 Server MessagePartnerName \> -AdapterMode 交互"**  
  
    * 结束  
  
    subsystem_stop:  
  
    * KILL9:snlreceiver  
  
    * 结束  
  
    subsystem_status:  
  
    * NB:1:snlreceiver  
  
    * 结束  
  
    start_event:SNL001:subsystem InteractStub 已启动  
  
    stop_event:SNL002:subsystem InteractStub 已关闭  
  
    \#subsystem_name:User  
  
    \## subsystem_group:user  
  
    \## subsystem_dependency:  
  
    \#subsystem_nature： 关键  
  
    \#subsystem_start:  
  
    \#* 结束  
  
    \#subsystem_stop:  
  
    \#* 结束  
  
    \#subsystem_status:  
  
    # <a name="end"></a>* 结束  
  
    # <a name="starteventsnl001subsystem-user-is-up"></a>start_event:SNL001:subsystem 用户已启动  
  
    # <a name="stopeventsnl002subsystem-user-is-down"></a>stop_event:SNL002:subsystem 用户已关闭  
  
## <a name="see-also"></a>请参阅  
 [InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md)   
 [步骤 1： 配置 SWIFT 适配器为 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md)   
 [步骤 3： 创建发送和接收端口的 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md)   
 [步骤 4：测试 InterAct 实时端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)