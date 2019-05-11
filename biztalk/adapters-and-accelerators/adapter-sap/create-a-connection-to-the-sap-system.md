---
title: 创建连接到 SAP 系统 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAP system, connecting to
- connection URI
- URI
- Uniform Resource Identifier
ms.assetid: 25d1eaa7-d02a-4fd0-8adf-83505cdb1ab8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58d823dda4b4697161a9f4e3df12f8cc48e97889
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373575"
---
# <a name="create-a-connection-to-the-sap-system"></a><span data-ttu-id="96e69-102">创建连接到 SAP 系统</span><span class="sxs-lookup"><span data-stu-id="96e69-102">Create a connection to the SAP system</span></span>
<span data-ttu-id="96e69-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="96e69-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="96e69-104">在这种情况下，它使到 SAP 系统通过 WCF 终结点地址的通信。</span><span class="sxs-lookup"><span data-stu-id="96e69-104">As such, it enables communication to an SAP system through a WCF endpoint address.</span></span> <span data-ttu-id="96e69-105">WCF 中的终结点地址标识服务的网络位置，并通常都表示为统一资源标识符 (URI)。</span><span class="sxs-lookup"><span data-stu-id="96e69-105">In WCF the endpoint address identifies the network location of a service and is typically expressed as a Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="96e69-106">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]表达此位置作为一个连接 URI，其中包含属性的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]用于建立到 SAP 系统的连接。</span><span class="sxs-lookup"><span data-stu-id="96e69-106">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expresses this location as a connection URI, which contains properties that the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses to establish a connection to the SAP system.</span></span> <span data-ttu-id="96e69-107">必须指定连接 URI 时您：</span><span class="sxs-lookup"><span data-stu-id="96e69-107">You must specify a connection URI when you:</span></span>  
  
- <span data-ttu-id="96e69-108">在创建通道工厂或通道侦听器使用[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型或创建使用 WCF 客户端或服务主机时[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型。</span><span class="sxs-lookup"><span data-stu-id="96e69-108">When you create a channel factory or a channel listener using the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] channel model or when you create a WCF client or service host using the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service model.</span></span>  
  
- <span data-ttu-id="96e69-109">创建中的一个物理端口绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。</span><span class="sxs-lookup"><span data-stu-id="96e69-109">Create a physical port binding in a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
- <span data-ttu-id="96e69-110">使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成 WCF 客户端类或 WCF 服务接口[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型解决方案。</span><span class="sxs-lookup"><span data-stu-id="96e69-110">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate a WCF client class or WCF service interface for a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service model solution.</span></span>  
  
- <span data-ttu-id="96e69-111">使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]来检索从消息架构[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]为[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。</span><span class="sxs-lookup"><span data-stu-id="96e69-111">Use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to retrieve message schemas from the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] for a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
- <span data-ttu-id="96e69-112">使用 ServiceModel 元数据实用工具工具 (svcutil.exe) 生成 WCF 客户端类或 WCF 服务模型解决方案的 WCF 服务接口。</span><span class="sxs-lookup"><span data-stu-id="96e69-112">Use the ServiceModel Metadata Utility tool (svcutil.exe) to generate a WCF client class or WCF service interface for a WCF service model solution.</span></span>  
  
  <span data-ttu-id="96e69-113">在本部分中的主题介绍如何建立之间的连接[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]和，它可以提供与 SAP 系统：</span><span class="sxs-lookup"><span data-stu-id="96e69-113">The topics in this section describe how to establish a connection between the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] and the SAP system by providing you with:</span></span>  
  
- <span data-ttu-id="96e69-114">有关连接属性和 SAP 连接 URI 的结构信息。</span><span class="sxs-lookup"><span data-stu-id="96e69-114">Information about the connection properties and the structure of the SAP connection URI.</span></span>  
  
- <span data-ttu-id="96e69-115">演示如何通过使用建立的连接的主题的链接[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="96e69-115">Links to topics that show how to establish a connection by using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="96e69-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="96e69-116">In This Section</span></span>  
  
-   [<span data-ttu-id="96e69-117">创建 SAP 系统连接 URI</span><span class="sxs-lookup"><span data-stu-id="96e69-117">Create the SAP system connection URI</span></span>](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)