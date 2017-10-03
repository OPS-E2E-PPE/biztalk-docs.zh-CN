---
title: "适配器中的架构生成 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, generating
- writing, schemas
ms.assetid: 43b69383-bae0-401b-9620-d4302db799b2
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d10d927e4ede59e716b3f9838c96bac8cd144a81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="schema-generation-in-the-adapter"></a>适配器中的架构生成
TIBCO Rendezvous 系统中没有消息类型存储库。 所有消息构造和解析都在 Rendezvous 应用程序级别隐藏了。 由于这个限制，用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器无法提供架构生成功能。  
  
## <a name="writing-schemas"></a>编写架构  
 你必须编写架构和使用**添加现有项**在 Visual Studio 中将其导入在业务流程中使用。 架构对于 BizTalk Server 开发工具和 Visual Studio 中的集成都非常重要。 BizTalk Server 开发人员可以选择提供完整架构、最低限要求的架构，或介于二者之间的版本。  
  
## <a name="see-also"></a>另请参阅  
 [入门](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)