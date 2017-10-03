---
title: "用于接收到的 Idoc 消息上下文属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDOCs, message context properties for receiving
ms.assetid: fadb2284-2f55-49c2-bae9-95325f1be539
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca289e37cac15972e75c69d7ad20928b72911963
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-context-properties-for-receiving-idocs"></a>用于接收到的 Idoc 的消息上下文属性
用于接收使用 Microsoft 的 IDOC [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持以下消息上下文属性。  
  
 **IDOC 控制记录的属性。**  
  
-   **TABNAM** -表结构的名称  
  
-   **MANDT** -客户端  
  
-   **DOCNUM** -IDOC 号码  
  
-   **DOCREL**的 IDOC 的 SAP 版本  
  
-   **状态**-的 IDOC 的状态  
  
-   **直接**-方向  
  
-   **OUTMOD** -输出模式  
  
-   **表达**-在入站处理过程中重写  
  
-   **测试**-测试标志  
  
-   **IDOCTYP** -基本类型的名称  
  
-   **CIMTYP** -（由客户定义） 的扩展  
  
-   **MESTYP** -消息类型  
  
-   **MESCOD** -消息代码  
  
-   **MESFCT** -消息函数  
  
-   **STD** -EDI 标准，标志  
  
-   **STDVRS** -EDI 标准，版本和发行版本  
  
-   **STDMES** -EDI 消息类型  
  
-   **SNDPOR** -发件人端口 （SAP 系统，外部子系统）  
  
-   **SNDPRT** -合作伙伴的发送程序类型  
  
-   **SNDPFC** -合作伙伴的发件人的函数  
  
-   **SNDPRN** -合作伙伴的发件人数  
  
-   **SNDSAD** -发件人地址 (SADR)  
  
-   **SNDLAD** -逻辑发件人地址  
  
-   **RCVPOR** -接收方端口  
  
-   **RCVPRT** -合作伙伴的接收方的类型  
  
-   **RCVPFC** -合作伙伴的收件人的函数  
  
-   **RCVPRN** -合作伙伴的接收方数  
  
-   **RCVSAD** -收件人地址 (SADR)  
  
-   **RCVLAD** -接收方的逻辑地址  
  
-   **CREDAT** -上创建  
  
-   **CRETIM**的创建时间  
  
-   **REFINT** -传输文件 （EDI 交换）  
  
-   **REFGRP** -消息组 （EDI 消息组）  
  
-   **REFMES** -消息 （EDI 消息）  
  
-   **ARCKEY** -密钥对于外部消息存档  
  
-   **串行**-序列化  
  
-   **DOCTYP** -IDOC 类型 （这仅提供 EDI_DC 版。 应出现在上下文属性，但应仅提升为版本 2 Idoc）  
  
 **TID** – 表示 SAP 系统发送的传入 TRFC 调用 TID。  
  
 **GUID** – 表示的 GUID 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在内部使用。 这具有与 TID SAP 系统从收到的一对一映射。  
  
## <a name="see-also"></a>另请参阅  
 [消息和用于 mySAP Business Suite 的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)