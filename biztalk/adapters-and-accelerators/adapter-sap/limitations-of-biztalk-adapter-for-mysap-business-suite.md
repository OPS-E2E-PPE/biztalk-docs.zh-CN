---
title: 为 mySAP Business Suite 的 BizTalk Adapter 限制 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, limitations of
- IDOC, sending an IDOC to an SAP system
ms.assetid: 1ca1e0cf-7ae7-4a8b-8363-e5f3746e8e26
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d392178cd49918151f0ad86c73a5fcba712d6b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217077"
---
# <a name="limitations-of-biztalk-adapter-for-mysap-business-suite"></a><span data-ttu-id="69d6d-102">为 mySAP Business Suite 的 BizTalk Adapter 限制</span><span class="sxs-lookup"><span data-stu-id="69d6d-102">Limitations of BizTalk Adapter for mySAP Business Suite</span></span>

## <a name="limitations-list"></a><span data-ttu-id="69d6d-103">限制列表</span><span class="sxs-lookup"><span data-stu-id="69d6d-103">Limitations list</span></span>
<span data-ttu-id="69d6d-104">以下已知的限制[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="69d6d-104">The following are known limitations of the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]:</span></span>  
  
-   <span data-ttu-id="69d6d-105">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不兼容与 Microsoft BizTalk 适配器为 mySAP Business Suite，以前的版本中的适配器。</span><span class="sxs-lookup"><span data-stu-id="69d6d-105">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is not compatible with Microsoft BizTalk Adapter for mySAP Business Suite, the previous release of the adapter.</span></span> <span data-ttu-id="69d6d-106">此版本的适配器不支持发送和接收具有使用适配器的早期版本生成的架构的消息。</span><span class="sxs-lookup"><span data-stu-id="69d6d-106">This release of the adapter does not support sending and receiving messages having schemas generated using the earlier version of the adapter.</span></span>  
  
-   <span data-ttu-id="69d6d-107">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不支持 Rfc 对具有复杂的参数类型，包括 ITAB II （分层） 的表类型。</span><span class="sxs-lookup"><span data-stu-id="69d6d-107">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not support RFCs with complex parameter types, including ITAB II (hierarchical) table types.</span></span>  
  
-   <span data-ttu-id="69d6d-108">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不支持具有自定义的 ABAP 类型的 Rfc。</span><span class="sxs-lookup"><span data-stu-id="69d6d-108">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not support RFCs having custom ABAP types.</span></span>  
  
-   <span data-ttu-id="69d6d-109">由于出现超时处理基础的客户端库，问题[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不支持命令和连接超时。</span><span class="sxs-lookup"><span data-stu-id="69d6d-109">Due to issues with timeout handling by the underlying client library, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not support command and connection timeout.</span></span>  
  
-   <span data-ttu-id="69d6d-110">如果你更改运行 BizTalk Server 主机的计算机的系统时间，时间不能在 BizTalk Server 主机中自动更新。</span><span class="sxs-lookup"><span data-stu-id="69d6d-110">If you change the system time of the computer running the BizTalk Server host, the time is not updated automatically in the BizTalk Server host.</span></span> <span data-ttu-id="69d6d-111">这可能导致不正确的行为，使用 BizTalk Server 接收端口的入站操作。</span><span class="sxs-lookup"><span data-stu-id="69d6d-111">This could lead to incorrect behavior of the inbound operations that use the receive port of BizTalk Server.</span></span> <span data-ttu-id="69d6d-112">一种解决方法，你必须重新启动后已更改运行它的计算机的系统时间具有接收端口、 主机实例。</span><span class="sxs-lookup"><span data-stu-id="69d6d-112">As a workaround, you must restart the host instance that has a receive port, after you have changed the system time of the computer running it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69d6d-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69d6d-113">See Also</span></span>  
 [<span data-ttu-id="69d6d-114">为 mySAP Business Suite 了解 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="69d6d-114">Understand BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)