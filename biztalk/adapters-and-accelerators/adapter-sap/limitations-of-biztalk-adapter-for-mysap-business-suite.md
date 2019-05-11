---
title: 用于 mySAP Business Suite 的 BizTalk 适配器的限制 |Microsoft Docs
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
ms.openlocfilehash: 828dbca3f4acba3ca76583c21e09bad3e79ba560
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373311"
---
# <a name="limitations-of-biztalk-adapter-for-mysap-business-suite"></a><span data-ttu-id="590d6-102">用于 mySAP Business Suite 的 BizTalk 适配器的限制</span><span class="sxs-lookup"><span data-stu-id="590d6-102">Limitations of BizTalk Adapter for mySAP Business Suite</span></span>

## <a name="limitations-list"></a><span data-ttu-id="590d6-103">限制列表</span><span class="sxs-lookup"><span data-stu-id="590d6-103">Limitations list</span></span>
<span data-ttu-id="590d6-104">以下已知的限制[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="590d6-104">The following are known limitations of the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]:</span></span>  
  
- <span data-ttu-id="590d6-105">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不兼容的 Microsoft BizTalk 适配器用于 mySAP Business Suite，以前版本的适配器。</span><span class="sxs-lookup"><span data-stu-id="590d6-105">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is not compatible with Microsoft BizTalk Adapter for mySAP Business Suite, the previous release of the adapter.</span></span> <span data-ttu-id="590d6-106">此版本的适配器不支持发送和接收具有使用适配器的早期版本生成的架构的消息。</span><span class="sxs-lookup"><span data-stu-id="590d6-106">This release of the adapter does not support sending and receiving messages having schemas generated using the earlier version of the adapter.</span></span>  
  
- <span data-ttu-id="590d6-107">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]具有复杂的参数类型，包括 ITAB II （分层） 的表类型中不支持 Rfc。</span><span class="sxs-lookup"><span data-stu-id="590d6-107">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not support RFCs with complex parameter types, including ITAB II (hierarchical) table types.</span></span>  
  
- <span data-ttu-id="590d6-108">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不支持 Rfc 具有自定义 ABAP 类型。</span><span class="sxs-lookup"><span data-stu-id="590d6-108">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not support RFCs having custom ABAP types.</span></span>  
  
- <span data-ttu-id="590d6-109">由于基础客户端库，超时处理问题[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不支持命令，并连接超时。</span><span class="sxs-lookup"><span data-stu-id="590d6-109">Due to issues with timeout handling by the underlying client library, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not support command and connection timeout.</span></span>  
  
- <span data-ttu-id="590d6-110">如果更改运行 BizTalk Server 主机的计算机的系统时间，时间不能在 BizTalk Server 主机中自动更新。</span><span class="sxs-lookup"><span data-stu-id="590d6-110">If you change the system time of the computer running the BizTalk Server host, the time is not updated automatically in the BizTalk Server host.</span></span> <span data-ttu-id="590d6-111">这可能会导致不正确的行为，使用 BizTalk Server 接收端口的入站操作。</span><span class="sxs-lookup"><span data-stu-id="590d6-111">This could lead to incorrect behavior of the inbound operations that use the receive port of BizTalk Server.</span></span> <span data-ttu-id="590d6-112">解决此问题，必须重新启动主机实例的接收端口中，更改运行它的计算机的系统时间之后。</span><span class="sxs-lookup"><span data-stu-id="590d6-112">As a workaround, you must restart the host instance that has a receive port, after you have changed the system time of the computer running it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="590d6-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="590d6-113">See Also</span></span>  
 [<span data-ttu-id="590d6-114">了解用于 mySAP Business Suite 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="590d6-114">Understand BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)