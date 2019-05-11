---
title: 创建与 Siebel 系统的连接 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connecting, to the Siebel system
ms.assetid: 5810eeb1-6e26-4620-a731-fb352eebea2e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57704a781776fb4e16689d454e367d38fd9da0ee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371756"
---
# <a name="create-a-connection-to-the-siebel-system"></a>创建与 Siebel 系统的连接
[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。 在这种情况下，它使到 Siebel 系统通过 WCF 终结点地址的通信。 WCF 中的终结点地址标识服务的网络位置，并通常都表示为统一资源标识符 (URI)。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]表达此位置作为一个连接 URI，其中包含属性的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]用于建立与 Siebel 系统的连接。 必须指定连接 URI 时您：  
  
- 创建通道工厂或通道侦听器使用[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型，或创建 WCF 客户端或服务主机使用[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型。  
  
- 创建中的一个物理端口绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。  
  
- 使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成 WCF 客户端类或 WCF 服务接口[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型解决方案。  
  
- 使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]来检索从消息架构[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]为[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。  
  
- 使用 ServiceModel 元数据实用工具工具 (svcutil.exe) 生成 WCF 客户端类或 WCF 服务模型解决方案的 WCF 服务接口。  
  
  在本部分中的主题介绍如何建立之间的连接[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]和，它可以提供与 Siebel 系统：  
  
- 有关连接属性和 Siebel 连接 URI 的结构信息。  
  
- 演示如何通过使用建立的连接的主题的链接[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  

  
## <a name="see-also"></a>请参阅  
[开发 Siebel 应用程序](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)