---
title: 消息和用于 Oracle E-business Suite 的 BizTalk 适配器的消息架构 |Microsoft Docs
description: Oracle EBS 适配器用于 BizTalk Server 的消息和数据类型的 XML 结构
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4434b4d4-fbe0-4692-81a5-9883c9a77cf6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0d21fa159295e6b8b38b53a98f18bc9b40c21db
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375368"
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite"></a>消息和消息架构用于 Oracle E-business Suite 的 BizTalk 适配器

## <a name="overview"></a>概述
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。 它公开应用程序可以调用在其上并且可以反过来，调用应用程序上的操作。 通过通道发送 SOAP 消息来调用这些操作。 如果响应是必需的它通过同一通道返回 SOAP 消息中。  
  
 作为[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开其操作和数据类型的元数据通过使用标准[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]机制。 本主题中的部分描述的消息的 XML 结构和数据类型，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [基本 Oracle 数据类型](../../adapters-and-accelerators/adapter-oracle-ebs/basic-oracle-data-types2.md)  
  
-   [插入、更新、删除和选择操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md)  
  
-   [存储过程、函数和 PL/SQL API 的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-stored-procedures-functions-and-pl-sql-apis.md)  
  
-   [并发程序的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-concurrent-programs.md)  
  
-   [请求集的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-request-sets.md)  
  
-   [特殊 LOB 操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-special-lob-operations1.md)  
  
-   [轮询操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-polling-operations1.md)  
  
-   [通知操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-notification-operation2.md)  
  
-   [ExecuteNonQuery、ExecuteReader 和 ExecuteScalar 操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/executenonquery-executereader-and-executescalar-message-schemas.md)  
  
-   [复合操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-composite-operation1.md)  
  