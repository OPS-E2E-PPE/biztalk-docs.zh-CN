---
title: 第 2 步：为 InterAct 存储和转发方案向 Paramfile 添加 SWIFTNet 配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a18a43c-1dd9-4113-bf32-8bc7bf9338b0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3bfa88c4a382721da5ccecc8baff2c2ebca2a50f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366197"
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-interact-store-and-forward-scenario"></a>第 2 步：为 InterAct 存储和转发方案向 Paramfile 添加 SWIFTNet 配置
在压降中创建的服务器消息合作伙伴必须指定 SWIFTNet paramfile 启用接收方可以使用这些值进行初始化。  
  
 在开始此步骤之前，必须完成[步骤 1:为 InterAct 存储和转发方案配置 SWIFT 适配器](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md)。  
  
### <a name="to-add-swiftnet-configuration-to-the-paramfile"></a>若要向 paramfile 添加 SWIFTNet 配置  
  
1. 在诸如记事本之类的文本编辑器中打开 paramfile。  
  
   > [!NOTE]
   >  Paramfile 是通常位于：C:\SWIFTAlliance\RA\Ra1\cfg\paramfile.  
  
2. 在 paramfile，请突出显示的更改来指定服务器消息合作伙伴名称：  
  
    username:snlowner  
  
    subsystem_name:InteractStub  
  
    \#subsystem_group:Interactsnf  
  
    \#subsystem_dependency:Support,Swarm  
  
    subsystem_nature:critical  
  
    subsystem_start:  
  
    **spawn "snlreceiver -SagMessagePartner \<Server MessagePartnerName for Interact SnF\> -AdapterMode Interact"**  
  
    * 结束  
  
    subsystem_stop:  
  
    *KILL9:snlreceiver  
  
    * 结束  
  
    subsystem_status:  
  
    *NB:1:snlreceiver  
  
    * 结束  
  
    start_event:SNL001:subsystem InteractStubSnF 已启动  
  
    stop_event:SNL002:subsystem InteractStubSnF 已关闭  
  
    \#subsystem_name:User  
  
    \##subsystem_group:user  
  
    \##subsystem_dependency:  
  
    \#subsystem_nature:critical  
  
    \#subsystem_start:  
  
    \#* 结束  
  
    \#subsystem_stop:  
  
    \#* 结束  
  
    \#subsystem_status:  
  
    \#* 结束  
  
    # <a name="starteventsnl001subsystem-user-is-up"></a>start_event:SNL001:subsystem 用户已启动  
  
    # <a name="stopeventsnl002subsystem-user-is-down"></a>stop_event:SNL002:subsystem 用户已关闭  
  
## <a name="see-also"></a>请参阅  
 [InterAct 存储和转发 （推送） 方案](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md)   
 [步骤 1：为 InterAct 存储和转发方案配置 SWIFT 适配器](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md)   
 [步骤 3：创建发送端口和接收端口为 InterAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [步骤 4：测试 InterAct 存储和转发端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)