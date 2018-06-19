---
title: 了解与 WCF LOB 适配器 SDK LOB 系统 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0f97846-5ef2-4530-853a-fba5469156f7
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d777022312c8511608519d155626c948da3efdb1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225797"
---
# <a name="understand-the-lob-system-with-the-wcf-lob-adapter-sdk"></a>了解 LOB 系统与 WCF LOB 适配器 SDK
之前你适配器使用开发[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，你必须具有目标业务线系统的全面了解。 如果你不了解业务线系统、 公开方式，以及提供有关安全、 事务和其他功能的支持的不同级别提供的功能，你的适配器可能无法提供所需的适配器的功能使用者。 本部分介绍你必须了解要有效地设计你的适配器的区域。  
  
## <a name="the-path-to-understanding"></a>了解到的路径  
 适配器的用途是以一致的、 可访问的方式根据适配器规范和/或适配器 API 所规定的规则中公开数据和从业务线系统的操作。 若要了解哪些操作和要公开的数据，必须了解系统的作用以及如何公开其数据和操作。 具体而言，您必须考虑以下设计问题：  
  
-   **连接生命周期。** 如何连接打开和关闭？ 如何打开维护的连接？ 是否有重复使用连接的特殊要求？ 有关连接的详细信息，请参阅`Microsoft.ServiceModel.Channels.Common.IConnection`。  
  
-   **公开系统的操作和类型元数据。** 不能业务线系统支持操作搜索和浏览并轻松访问元数据，或者必须开发支持代码来提供此功能？ 例如，在 SQL Server 操作为对象，如存储过程。 有关列、 表和其他对象的类型元数据很容易检索。 旧的业务线系统可能会更加难以使用。  
  
-   **如何通过系统公开的操作和数据。** 如何公开 API？ 阻止 （同步） 的 API 支持和非阻止 （异步） 调用？ 回调支持？ 你将接口的 API 或协议级别？  
  
-   **安全、 事务和可靠的消息传送支持。** 如果该 API 支持这些功能，你可能想要将它们公开给适配器使用者。 例如，SQL Server 具有安全和事务支持，尽管可靠消息传递变得不实用 （但会使用 MSMQ 或某些其他队列系统）。  
  
-   **哪些功能和使用情况的方案非常重要？** 不限制到纯粹技术; 你了解讨论并捕获的业务要求与有经验的用户。 是否有任何施加某些操作的唯一约束？ 是否有尚不明确的操作很有用？ 很少使用某些功能？  
  
 若要了解此信息，你应目标业务线系统中查阅的用户和技术文档。 如果文档是稀疏的还是缺少，你可能还会能够了解系统的技术方面，通过查看在线支持论坛、 联机新闻组、 博客，或通过检查实现详细信息的安装文件。 如果你有权访问的业务线开发人员或代码文件，你可能能够发现你需要包括连接语义、 安全，支持和如何搜索和调用操作的信息。  
  
## <a name="see-also"></a>另请参阅  
 [规划和设计你使用 WCF LOB 适配器 SDK 的适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-your-adapter-using-the-wcf-lob-adapter-sdk.md)   
 [要开始使用与 WCF LOB 适配器 SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/get-started-with-the-with-the-wcf-lob-adapter-sdk.md)   
 [选择合适的框架](https://msdn.microsoft.com/library/bb798089.aspx)