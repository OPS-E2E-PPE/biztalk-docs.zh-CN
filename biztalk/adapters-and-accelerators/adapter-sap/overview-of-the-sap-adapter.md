---
title: SAP 适配器概述 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, overview
ms.assetid: 2d078b13-d41f-476f-bfb4-82be4d35a769
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3031bdf1317d96f64f1ea247c6f8cbf83e1688c7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963027"
---
# <a name="overview-of-the-sap-adapter"></a><span data-ttu-id="c5cda-102">SAP 适配器的概述</span><span class="sxs-lookup"><span data-stu-id="c5cda-102">Overview of the SAP adapter</span></span>
<span data-ttu-id="c5cda-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]公开 SAP 系统作为 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="c5cda-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] exposes the SAP system as a WCF service.</span></span> <span data-ttu-id="c5cda-104">适配器客户端可以通过交换 SOAP 消息与适配器执行 SAP 系统上的操作。</span><span class="sxs-lookup"><span data-stu-id="c5cda-104">Adapter clients can perform operations on the SAP system by exchanging SOAP messages with the adapter.</span></span> <span data-ttu-id="c5cda-105">适配器使用 WCF 消息，并且到 SAP 系统的适当调用来执行该操作。</span><span class="sxs-lookup"><span data-stu-id="c5cda-105">The adapter consumes the WCF message and makes appropriate calls to the SAP system to perform the operation.</span></span> <span data-ttu-id="c5cda-106">适配器回客户端的 SOAP 消息的形式，并将响应返回从 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="c5cda-106">The adapter returns the response from the SAP system back to the client in the form of SOAP messages.</span></span>  
  
 <span data-ttu-id="c5cda-107">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]曲面元数据的 SAP 项目 (RFC，BAPI，IDOC) 描述的结构的 SOAP 消息的 WSDL 形式。</span><span class="sxs-lookup"><span data-stu-id="c5cda-107">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces metadata of SAP artifacts (RFC, BAPI, IDOC) that describes the structure of a SOAP message in the form of WSDL.</span></span> <span data-ttu-id="c5cda-108">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]才能使适配器客户端检索操作的元数据并在编程解决方案中生成可用的编程项目。</span><span class="sxs-lookup"><span data-stu-id="c5cda-108">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to enable adapter clients to retrieve metadata for operations and generates programming artifacts that can be used in your programming solution.</span></span> <span data-ttu-id="c5cda-109">有关详细信息[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，请参阅[连接到 Visual Studio 中的 SAP 系统](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="c5cda-109">For more information about [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], see [Connect to the SAP System in Visual Studio](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md).</span></span>  
  
 <span data-ttu-id="c5cda-110">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用 Unicode RFC 库，librfc32u.dll，与 SAP 系统，除了使用其他支持 Dll 进行通信。</span><span class="sxs-lookup"><span data-stu-id="c5cda-110">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses the Unicode RFC library, librfc32u.dll, to communicate with the SAP system, in addition to using other supporting DLLs.</span></span> <span data-ttu-id="c5cda-111">有关 SAP 适配器需要的 Dll 的完整列表，请参阅[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装指南。</span><span class="sxs-lookup"><span data-stu-id="c5cda-111">For a complete list of SAP DLLs that the adapter requires, see the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation guide.</span></span> <span data-ttu-id="c5cda-112">安装指南通常安装在\<安装驱动器：\>\Program Files\\[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents。</span><span class="sxs-lookup"><span data-stu-id="c5cda-112">The installation guide is typically installed at \<installation drive:\>\Program Files\\[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.</span></span> <span data-ttu-id="c5cda-113">你可以使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]以下列方式与 SAP 系统进行通信：</span><span class="sxs-lookup"><span data-stu-id="c5cda-113">You can use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to communicate with the SAP system in the following ways:</span></span>  
  
-   <span data-ttu-id="c5cda-114">通过开发 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="c5cda-114">By developing BizTalk applications.</span></span> <span data-ttu-id="c5cda-115">请参阅[开发 BizTalk 服务器应用程序](../../core/developing-biztalk-server-applications.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="c5cda-115">See [Developing BizTalk Server Applications](../../core/developing-biztalk-server-applications.md) for more information.</span></span>  
  
-   <span data-ttu-id="c5cda-116">通过使用[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]服务模型。</span><span class="sxs-lookup"><span data-stu-id="c5cda-116">By using the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] service model.</span></span> <span data-ttu-id="c5cda-117">请参阅[开发 SAP 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="c5cda-117">See [Develop SAP applications using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md).</span></span>
  
-   <span data-ttu-id="c5cda-118">通过使用 WCF 通道模型。</span><span class="sxs-lookup"><span data-stu-id="c5cda-118">By using the WCF channel model.</span></span> <span data-ttu-id="c5cda-119">请参阅[开发 SAP 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)。</span><span class="sxs-lookup"><span data-stu-id="c5cda-119">See [Develop SAP applications using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="c5cda-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="c5cda-120">In This Section</span></span>  
  
-   [<span data-ttu-id="c5cda-121">适配器如何连接到 SAP 系统？</span><span class="sxs-lookup"><span data-stu-id="c5cda-121">How Does the Adapter Connect to an SAP System?</span></span>](https://msdn.microsoft.com/library/cc185540.aspx)  
  
-   [<span data-ttu-id="c5cda-122">原理适配器图面 SAP 元数据是什么？</span><span class="sxs-lookup"><span data-stu-id="c5cda-122">How Does the Adapter Surface SAP Metadata?</span></span>](https://msdn.microsoft.com/library/dd788039.aspx)  
  
-   [<span data-ttu-id="c5cda-123">哪些操作可以是执行使用适配器？</span><span class="sxs-lookup"><span data-stu-id="c5cda-123">What Operations Can be Performed Using the Adapter?</span></span>](https://msdn.microsoft.com/library/dd788159.aspx)  
  
-   [<span data-ttu-id="c5cda-124">适配器支持的其他功能</span><span class="sxs-lookup"><span data-stu-id="c5cda-124">Other Features Supported by the Adapter</span></span>](https://msdn.microsoft.com/library/dd788022.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="c5cda-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5cda-125">See Also</span></span>  
 [<span data-ttu-id="c5cda-126">了解用于 mySAP Business Suite 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="c5cda-126">Understand BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)