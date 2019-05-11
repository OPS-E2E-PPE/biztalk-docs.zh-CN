---
title: 安装、 架构和限制 TIBCO Rendezvous 适配器 |Microsoft Docs
description: 安装、 架构生成和用于在 BizTalk Server 中的 TIBCO Rendezvous 的 BizTalk 适配器的限制
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6404e7e-f671-4c57-a222-0bbe7cbc334f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f00e77a4eb2234265430f3cadc6a8384d768d16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382082"
---
# <a name="install-schemas-and-limitations-of-the-tibco-rendezvous-adapter"></a>安装、 架构和 TIBCO Rendezvous 适配器限制

## <a name="install-and-setup"></a>安装和设置

[安装和配置企业应用程序的适配器](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md)包括安装企业适配器的步骤，还包括关键信息，了解安装适配器之前和之后安装适配器。 

## <a name="generate-schemas"></a>生成架构
TIBCO Rendezvous 系统不包括消息类型存储库。 所有消息构造和分析隐藏在 Rendezvous 应用程序级别的信息。 鉴于此限制，适配器不能提供架构生成功能。  
  
必须编写一个架构，并使用**添加现有项**在 Visual Studio 中将其导入在业务流程中使用。 架构是 BizTalk Server 开发工具和 Visual Studio 中的集成非常重要。 BizTalk Server 开发人员可以选择提供完整的架构、 最低要求的架构或二者之间的版本之间。  

## <a name="limitations"></a>限制

- 不能保证字段名的唯一性。 如果 TIBCO Rendezvous 消息包含两个相同的名称字段，则结果 XML 无效。  
  
- 未提供字段排序功能。  
  
- 根据 TIBCO Rendezvous 文档，使用者名称中不会使用非打印的字符；但是仍可能使用这样的字符。 用于 TIBCO Rendezvous 的 BizTalk 适配器不支持包含这些字符的使用者名称。  
  
- 不支持与后台程序的安全连接。  
  
- 不支持自定义数据类型。  
  
- 传输端不支持经过验证的消息。  
- 
  ## <a name="next-step"></a>下一步

[教程：使用用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md)  