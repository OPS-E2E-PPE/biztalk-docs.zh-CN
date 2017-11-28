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
# <a name="create-a-connection-to-the-sap-system"></a><span data-ttu-id="d09eb-102">创建与 SAP 系统的连接</span><span class="sxs-lookup"><span data-stu-id="d09eb-102">Create a connection to the SAP system</span></span>
<span data-ttu-id="d09eb-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="d09eb-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="d09eb-104">在这种情况下，它使到 SAP 系统通过 WCF 终结点地址的通信。</span><span class="sxs-lookup"><span data-stu-id="d09eb-104">As such, it enables communication to an SAP system through a WCF endpoint address.</span></span> <span data-ttu-id="d09eb-105">在 WCF 中的终结点地址标识服务的网络位置，并通常表示为统一资源标识符 (URI)。</span><span class="sxs-lookup"><span data-stu-id="d09eb-105">In WCF the endpoint address identifies the network location of a service and is typically expressed as a Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="d09eb-106">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]表示此位置作为连接 URI，其中包含属性的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]用于建立到 SAP 系统的连接。</span><span class="sxs-lookup"><span data-stu-id="d09eb-106">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expresses this location as a connection URI, which contains properties that the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses to establish a connection to the SAP system.</span></span> <span data-ttu-id="d09eb-107">必须指定连接 URI 时你：</span><span class="sxs-lookup"><span data-stu-id="d09eb-107">You must specify a connection URI when you:</span></span>  
  
-   <span data-ttu-id="d09eb-108">当你创建的通道工厂或通道侦听器使用[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型或当你创建使用 WCF 客户端或服务主机[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型。</span><span class="sxs-lookup"><span data-stu-id="d09eb-108">When you create a channel factory or a channel listener using the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] channel model or when you create a WCF client or service host using the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service model.</span></span>  
  
-   <span data-ttu-id="d09eb-109">创建中的物理端口绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。</span><span class="sxs-lookup"><span data-stu-id="d09eb-109">Create a physical port binding in a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
-   <span data-ttu-id="d09eb-110">使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成 WCF 客户端类或 WCF 服务接口[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型解决方案。</span><span class="sxs-lookup"><span data-stu-id="d09eb-110">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate a WCF client class or WCF service interface for a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service model solution.</span></span>  
  
-   <span data-ttu-id="d09eb-111">使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]检索消息架构从[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]为[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。</span><span class="sxs-lookup"><span data-stu-id="d09eb-111">Use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to retrieve message schemas from the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] for a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
-   <span data-ttu-id="d09eb-112">使用 ServiceModel 元数据实用工具 (svcutil.exe) 生成 WCF 客户端类或 WCF 服务模型解决方案的 WCF 服务接口。</span><span class="sxs-lookup"><span data-stu-id="d09eb-112">Use the ServiceModel Metadata Utility tool (svcutil.exe) to generate a WCF client class or WCF service interface for a WCF service model solution.</span></span>  
  
 <span data-ttu-id="d09eb-113">本部分中的主题介绍如何之间建立连接[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]和 SAP 系统，它可以提供与：</span><span class="sxs-lookup"><span data-stu-id="d09eb-113">The topics in this section describe how to establish a connection between the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] and the SAP system by providing you with:</span></span>  
  
-   <span data-ttu-id="d09eb-114">有关连接属性和 SAP 连接 URI 的结构信息。</span><span class="sxs-lookup"><span data-stu-id="d09eb-114">Information about the connection properties and the structure of the SAP connection URI.</span></span>  
  
-   <span data-ttu-id="d09eb-115">演示如何通过使用建立连接的主题的链接[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d09eb-115">Links to topics that show how to establish a connection by using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d09eb-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="d09eb-116">In This Section</span></span>  
  
-   [<span data-ttu-id="d09eb-117">创建 SAP 系统连接 URI</span><span class="sxs-lookup"><span data-stu-id="d09eb-117">Create the SAP system connection URI</span></span>](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)