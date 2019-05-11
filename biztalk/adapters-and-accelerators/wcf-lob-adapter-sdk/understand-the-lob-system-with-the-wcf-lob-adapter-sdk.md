---
title: 了解 WCF LOB 适配器 SDK 与 LOB 系统 |Microsoft Docs
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
ms.openlocfilehash: 1a3a3a44292c3c439c7556bd14e7aa7acadd4fdc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362731"
---
# <a name="understand-the-lob-system-with-the-wcf-lob-adapter-sdk"></a>了解 LOB 系统与 WCF LOB 适配器 SDK
开发适配器使用之前[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，您必须全面了解目标业务线系统。 如果您不了解提供业务线系统、 公开方式和提供安全、 事务和其他功能的支持的不同级别的功能，您的适配器可能无法提供所需的适配器的功能使用者。 本部分介绍必须了解要高效地设计您的适配器的区域。  
  
## <a name="the-path-to-understanding"></a>了解到的路径  
 适配器的用途是公开的数据和操作的业务线系统以一致、 可访问的方式根据适配器规范和/或适配器 API 所规定的规则。 若要了解哪些操作和要公开的数据，必须了解系统的作用以及如何公开其数据和操作。 具体而言，您必须考虑以下设计问题：  
  
- **连接生命周期。** 如何连接打开和关闭？ 如何维护打开的连接？ 是否有重复使用一个连接的特殊要求？ 有关连接的详细信息，请参阅`Microsoft.ServiceModel.Channels.Common.IConnection`。  
  
- **由系统公开的操作和类型元数据。** 不能在业务线系统支持操作搜索和浏览和轻松访问元数据，或者您必须开发的支持代码来提供此功能？ 例如，在 SQL Server 操作的对象，如存储过程。 有关列、 表和其他对象的类型元数据可轻松地检索。 旧的业务线系统可能更难以使用。  
  
- **如何将操作和数据公开由系统中。** 如何公开 API？ 阻止 （同步） 的 API 支持和非阻塞 （异步） 调用？ 回调支持？ 是否需要将 API 或协议级别？  
  
- **对安全性、 事务和可靠的消息传送支持。** 如果该 API 支持这些功能，您可能想要将它们公开给适配器使用者。 例如，SQL Server 具有安全性和事务支持尽管可靠消息传送是不切实际的 （但会将与 MSMQ 或某些其他队列系统）。  
  
- **哪些功能和使用情况的方案非常重要？** 不限制您的理解对纯技术;讨论并捕获业务要求与有经验的用户。 是否有任何唯一约束施加某些操作？ 是否有尚不明确的操作很有用？ 很少使用某些功能？  
  
  若要了解此信息，应为目标的业务线系统咨询用户和技术文档。 如果文档是稀疏的还是缺少，可能还能够了解系统的技术方面，通过查找联机支持论坛、 在线新闻组、 博客，或检查有关实施详细信息的安装文件。 如果你有权访问的业务线开发人员或代码文件，您可能能够发现您需要包括连接语义、 支持安全，以及如何搜索和调用操作的信息。  
  
## <a name="see-also"></a>请参阅  
 [规划和设计您的适配器使用 WCF LOB 适配器 SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-your-adapter-using-the-wcf-lob-adapter-sdk.md)   
 [开始使用与 WCF LOB 适配器 SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/get-started-with-the-with-the-wcf-lob-adapter-sdk.md)   
 [选择合适的框架](https://msdn.microsoft.com/library/bb798089.aspx)