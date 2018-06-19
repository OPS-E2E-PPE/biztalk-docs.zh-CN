---
title: 管理使用 WCF LOB 适配器 SDK 适配器进行版本控制 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb596fdd-251c-4978-9f33-cf2883d281d8
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf8d5d13c37f683a118484c9c08fa90c13a95533
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225829"
---
# <a name="manage-adapter-versioning-with-the-wcf-lob-adapter-sdk"></a>管理使用 WCF LOB 适配器 SDK 适配器进行版本控制
初始部署之后的适配器和在其生存期期间可能多次，可能需要更改的原因有多种多样适配器 （和它们公开的终结点）。 这些原因包括更改业务需求、 信息技术要求或与业务系统或适配器本身的行的问题。 本主题讨论不同的策略来处理使用编写的适配器的版本控制[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]。  
  
## <a name="versioning-and-windows-communication-foundation"></a>版本控制和 Windows Communication Foundation  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]基于[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]，并依赖于其基础结构，以便系统之间交换消息。 使用机制，[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]公开，你可以版本服务和数据协定。 有关详细信息，包括服务版本控制的最佳实践，请参阅[服务版本控制](http://go.microsoft.com/fwlink/?LinkId=85497)中[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]联机引用。 有关详细信息，包括最佳实践数据协定版本管理，请参阅[数据协定版本管理](http://go.microsoft.com/fwlink/?LinkId=120177)中[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]联机引用。  
  
## <a name="versioning-scenarios"></a>版本控制方案  
 有两个主版本控制方案：  
  
-   一个适配器版本支持目标系统的多个的版本。  
  
-   两个或多个适配器版本支持相同的系统或两个或多个不同的系统。  
  
 你可能还需要发布你的适配器的新版本，如果更新到[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]影响现有功能。  
  
 每种方案需要有一个不同的版本控制策略。  
  
> [!NOTE]
>  [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]不强制实施任何特定版本管理方案。 它是从左到开发人员确定适配器的版本控制要求。  
  
### <a name="one-adapter-supports-multiple-versions-of-target-system"></a>一个适配器支持多个版本的目标系统  
 当适配器支持多个版本的目标系统时，应公开可用于标识所需的版本的一个或多个绑定属性。 例如，一个适配器可能支持目标系统的供应商提供的多个通信库。 适配器使用者使用名为"LibraryVersion"的自定义绑定属性，可以选择要使用其中库基于部署环境或其他需求。  
  
### <a name="two-or-more-adapters-support-one-version-of-target-system"></a>两个或多个适配器支持目标系统的一个的版本  
 在这种情况下，每个适配器应使用唯一的方案 (ContosoV1: / / 和 ContosoV2: / /) 和一个唯一的绑定名称 （ContosoV1Binding 和 ContosoV2Binding）。 供应商应考虑使用中的方案和绑定名称以及 （例如，Microsoft.ContosoV1:// 和 Microsoft.ContosoV1Binding） 其名称。  
  
### <a name="new-versions-of-the-wcf-lob-adapter-sdk"></a>新版本的 WCF LOB 适配器 SDK  
 当新版本的[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是发布，你将能够安装新版本，而无需重新编译你的适配器，因为[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]版本都是向后兼容。 但是，应评估新的版本，以确定是否更改的功能，你的适配器依赖或者如果你的适配器会带来好处实现的新功能。  
  
## <a name="see-also"></a>另请参阅  
 [使用 WCF LOB 适配器 SDK 开发最佳做法](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)