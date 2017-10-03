---
title: "协议解析失败，协议基于上下文属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58fccd84-579c-4b5e-872b-33730d4079e8
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76d74ad7aa4a73f4a0befcef32bc8051195cb080
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# 基于协议上下文属性的协议解析失败
## 详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|AgreementResolutionContextPropertiesLookupFailed|  
|消息正文|协议解析基于的 {0} 协议已失败的上下文属性。|  
  
## 解释  
 此错误/警告/信息事件表明 BizTalk Server 无法基于客户提供的上下文属性解析为协议。  
  
## 用户操作  
 若要解决此错误，请作为 BizTalk 消息的一部分提供上下文属性，以便可以进行协议解析。