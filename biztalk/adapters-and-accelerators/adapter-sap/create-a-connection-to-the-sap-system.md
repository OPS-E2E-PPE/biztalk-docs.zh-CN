---
title: "创建与 SAP 系统的连接 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SAP system, connecting to
- connection URI
- URI
- Uniform Resource Identifier
ms.assetid: 25d1eaa7-d02a-4fd0-8adf-83505cdb1ab8
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9835047fd32556e6bd9f42adb768ce62f4536ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="create-a-connection-to-the-sap-system"></a>创建与 SAP 系统的连接
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。 在这种情况下，它使到 SAP 系统通过 WCF 终结点地址的通信。 在 WCF 中的终结点地址标识服务的网络位置，并通常表示为统一资源标识符 (URI)。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]表示此位置作为连接 URI，其中包含属性的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]用于建立到 SAP 系统的连接。 必须指定连接 URI 时你：  
  
-   当你创建的通道工厂或通道侦听器使用[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型或当你创建使用 WCF 客户端或服务主机[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型。  
  
-   创建中的物理端口绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。  
  
-   使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成 WCF 客户端类或 WCF 服务接口[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型解决方案。  
  
-   使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]检索消息架构从[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]为[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。  
  
-   使用 ServiceModel 元数据实用工具 (svcutil.exe) 生成 WCF 客户端类或 WCF 服务模型解决方案的 WCF 服务接口。  
  
 本部分中的主题介绍如何之间建立连接[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]和 SAP 系统，它可以提供与：  
  
-   有关连接属性和 SAP 连接 URI 的结构信息。  
  
-   演示如何通过使用建立连接的主题的链接[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)