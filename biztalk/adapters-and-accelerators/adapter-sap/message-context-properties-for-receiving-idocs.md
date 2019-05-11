---
title: 用于接收 Idoc 消息上下文属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDOCs, message context properties for receiving
ms.assetid: fadb2284-2f55-49c2-bae9-95325f1be539
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5468a1944ecfb4e2ae3da2ded5d941d19ac37712
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373262"
---
# <a name="message-context-properties-for-receiving-idocs"></a>用于接收 Idoc 的消息上下文属性
用于接收 IDOC 使用 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，则[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持以下消息上下文属性。  
  
 **IDOC 控制记录的属性。**  
  
- **TABNAM** -表结构的名称  
  
- **MANDT** -客户端  
  
- **DOCNUM** -IDOC 号码  
  
- **DOCREL** -SAP 的 IDOC 版本  
  
- **状态**-IDOC 的状态  
  
- **直接**-方向  
  
- **OUTMOD** -输出模式  
  
- **表达**-入站处理中重写  
  
- **测试**-测试标志  
  
- **IDOCTYP** -基本类型的名称  
  
- **CIMTYP** -扩展 （由客户定义）  
  
- **MESTYP** -消息类型  
  
- **MESCOD** -消息代码  
  
- **MESFCT** -消息函数  
  
- **标准**-EDI 标准，标志  
  
- **STDVRS** -EDI 标准、 版本和发行版本  
  
- **STDMES**的 EDI 消息类型  
  
- **SNDPOR** -发件人端口 （SAP 系统，外部子系统）  
  
- **SNDPRT** -合作伙伴的发送程序类型  
  
- **SNDPFC** -合作伙伴的发件人的函数  
  
- **SNDPRN** -合作伙伴的发送方数  
  
- **SNDSAD** -发件人地址 (SADR)  
  
- **SNDLAD** -逻辑发件人地址  
  
- **RCVPOR** -接收端口  
  
- **RCVPRT** -接收方的合作伙伴类型  
  
- **RCVPFC** -合作伙伴的接收方的函数  
  
- **RCVPRN** -合作伙伴的接收方数  
  
- **RCVSAD** -收件人地址 (SADR)  
  
- **RCVLAD** -收件人的逻辑地址  
  
- **CREDAT** -在上创建的  
  
- **CRETIM**的创建时间  
  
- **REFINT** -传输文件 （EDI 交换）  
  
- **REFGRP** -消息组 （EDI 消息组）  
  
- **REFMES** -消息 （EDI 消息）  
  
- **ARCKEY** -密钥对外部消息存档  
  
- **串行**-序列化  
  
- **DOCTYP** -IDOC 类型 （这仅提供 EDI_DC。 应为上下文属性中存在，但应仅升级为版本 2 Idoc）  
  
  **TID** – 表示 SAP 系统发送传入 TRFC 调用 TID。  
  
  **GUID** – 表示 GUID 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在内部使用。 这具有 TID 这来自 SAP 系统具有一对一的映射。  
  
## <a name="see-also"></a>请参阅  
 [消息和消息架构用于 mySAP Business Suite 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)