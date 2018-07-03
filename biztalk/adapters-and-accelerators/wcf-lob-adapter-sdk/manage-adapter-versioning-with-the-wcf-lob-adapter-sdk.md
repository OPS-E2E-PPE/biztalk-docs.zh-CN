---
title: 管理适配器使用 WCF LOB 适配器 SDK 的版本控制 |Microsoft Docs
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
ms.openlocfilehash: 8dfb323bf810f69c8a8f1f857b0d0240c14c4d18
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975182"
---
# <a name="manage-adapter-versioning-with-the-wcf-lob-adapter-sdk"></a>管理适配器使用 WCF LOB 适配器 SDK 的版本控制
初始部署之后的适配器和在其生存期期间可能会几次，可能需要更改的原因有多种适配器 （和它们公开的终结点）。 由于这些原因包括更改的业务需求、 信息技术需求或业务系统或适配器本身的行的问题。 本主题讨论了不同的策略来处理使用编写的适配器的版本控制[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]。  
  
## <a name="versioning-and-windows-communication-foundation"></a>版本控制和 Windows Communication Foundation  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]基于[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]，依赖于其基础结构以系统间交换消息。 使用的机制，[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]公开，可以确定版本服务和数据协定。 有关详细信息，其中包括最佳实践服务版本控制，请参阅[服务版本控制](http://go.microsoft.com/fwlink/?LinkId=85497)中[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]联机参考。 有关详细信息，其中包括最佳实践数据协定版本管理，请参阅[数据协定版本管理](http://go.microsoft.com/fwlink/?LinkId=120177)中[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]联机参考。  
  
## <a name="versioning-scenarios"></a>版本控制方案  
 有两个主版本控制方案：  
  
- 一个适配器版本支持多个版本的目标系统。  
  
- 两个或多个在适配器各版本支持在同一系统或两个或多个不同的系统。  
  
  您可能还需要发布您的适配器的新版本，如果更新到[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]会影响现有功能。  
  
  每种方案需要不同的版本控制策略。  
  
> [!NOTE]
>  [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]不强制实施任何特定的版本控制方案。 它由开发人员决定的适配器版本控制要求。  
  
### <a name="one-adapter-supports-multiple-versions-of-target-system"></a>一个适配器支持多个版本的目标系统  
 当适配器支持多个版本的目标系统时，应公开可用于标识所需的版本的一个或多个绑定属性。 例如，适配器可能支持由目标系统的供应商提供的多个通信库。 使用名为"LibraryVersion"的自定义绑定属性，适配器使用者可以选择要使用的库基于部署环境或其他要求。  
  
### <a name="two-or-more-adapters-support-one-version-of-target-system"></a>两个或多个适配器支持目标系统的一个的版本  
 在这种情况下，每个适配器应使用唯一的方案 (ContosoV1: / / 和 ContosoV2: / /) 和唯一绑定名称 （ContosoV1Binding 和 ContosoV2Binding）。 供应商应考虑使用方案和绑定名称也 （例如，Microsoft.ContosoV1:// 和 Microsoft.ContosoV1Binding） 中的其名称。  
  
### <a name="new-versions-of-the-wcf-lob-adapter-sdk"></a>WCF LOB 适配器 SDK 的新版本  
 当新版本的[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是发布，您将能够安装新版本，而无需重新编译您的适配器，因为[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]发布是可向后兼容。 但是，您应评估新版本以确定是否存在，取决于您的适配器的功能中的更改或如果您的适配器受益于实现的新功能。  
  
## <a name="see-also"></a>请参阅  
 [使用 WCF LOB 适配器 SDK 开发最佳做法](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)