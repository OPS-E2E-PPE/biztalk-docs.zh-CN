---
title: SAP 适配器概述 |Microsoft Docs
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
ms.openlocfilehash: 271b733430b1b31828903add62bd8d71318abafb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373140"
---
# <a name="overview-of-the-sap-adapter"></a><span data-ttu-id="9505e-102">SAP 适配器概述</span><span class="sxs-lookup"><span data-stu-id="9505e-102">Overview of the SAP adapter</span></span>
<span data-ttu-id="9505e-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]公开为 WCF 服务的 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="9505e-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] exposes the SAP system as a WCF service.</span></span> <span data-ttu-id="9505e-104">适配器客户端可以通过该适配器与交换的 SOAP 消息执行 SAP 系统的操作。</span><span class="sxs-lookup"><span data-stu-id="9505e-104">Adapter clients can perform operations on the SAP system by exchanging SOAP messages with the adapter.</span></span> <span data-ttu-id="9505e-105">适配器使用 WCF 消息并进行相应调用到 SAP 系统，以执行操作。</span><span class="sxs-lookup"><span data-stu-id="9505e-105">The adapter consumes the WCF message and makes appropriate calls to the SAP system to perform the operation.</span></span> <span data-ttu-id="9505e-106">适配器返回到 SOAP 消息的窗体中的客户端从 SAP 系统返回的响应。</span><span class="sxs-lookup"><span data-stu-id="9505e-106">The adapter returns the response from the SAP system back to the client in the form of SOAP messages.</span></span>  
  
 <span data-ttu-id="9505e-107">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]曲面的 SAP 项目 (RFC，BAPI，IDOC) 描述的元数据结构的 SOAP 消息的 WSDL 格式。</span><span class="sxs-lookup"><span data-stu-id="9505e-107">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces metadata of SAP artifacts (RFC, BAPI, IDOC) that describes the structure of a SOAP message in the form of WSDL.</span></span> <span data-ttu-id="9505e-108">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]启用适配器客户端来检索操作的元数据，并在生成的编程项目，可以使用编程解决方案中。</span><span class="sxs-lookup"><span data-stu-id="9505e-108">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to enable adapter clients to retrieve metadata for operations and generates programming artifacts that can be used in your programming solution.</span></span> <span data-ttu-id="9505e-109">有关详细信息[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，并[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，请参阅[连接到 Visual Studio 中的 SAP 系统](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="9505e-109">For more information about [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], see [Connect to the SAP System in Visual Studio](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md).</span></span>  
  
 <span data-ttu-id="9505e-110">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用 Unicode RFC 库，librfc32u.dll，与 SAP 系统，除了使用其他支持的 Dll 进行通信。</span><span class="sxs-lookup"><span data-stu-id="9505e-110">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses the Unicode RFC library, librfc32u.dll, to communicate with the SAP system, in addition to using other supporting DLLs.</span></span> <span data-ttu-id="9505e-111">SAP 适配器需要的 Dll 的完整列表，请参阅[BizTalk 适配器包安装指南](../../adapters-and-accelerators/biztalk-adapter-pack.md#install-bap)。</span><span class="sxs-lookup"><span data-stu-id="9505e-111">For a complete list of SAP DLLs that the adapter requires, see the [BizTalk Adapter Pack installation guide](../../adapters-and-accelerators/biztalk-adapter-pack.md#install-bap).</span></span> <span data-ttu-id="9505e-112">可以使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]以以下方式与 SAP 系统进行通信：</span><span class="sxs-lookup"><span data-stu-id="9505e-112">You can use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to communicate with the SAP system in the following ways:</span></span>  
  
- <span data-ttu-id="9505e-113">通过开发 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="9505e-113">By developing BizTalk applications.</span></span> <span data-ttu-id="9505e-114">请参阅[开发 BizTalk Server 应用程序](../../core/developing-biztalk-server-applications.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="9505e-114">See [Developing BizTalk Server Applications](../../core/developing-biztalk-server-applications.md) for more information.</span></span>  
  
- <span data-ttu-id="9505e-115">通过使用[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]服务模型。</span><span class="sxs-lookup"><span data-stu-id="9505e-115">By using the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] service model.</span></span> <span data-ttu-id="9505e-116">请参阅[开发 SAP 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="9505e-116">See [Develop SAP applications using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md).</span></span>
  
- <span data-ttu-id="9505e-117">通过使用 WCF 通道模型。</span><span class="sxs-lookup"><span data-stu-id="9505e-117">By using the WCF channel model.</span></span> <span data-ttu-id="9505e-118">请参阅[开发 SAP 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)。</span><span class="sxs-lookup"><span data-stu-id="9505e-118">See [Develop SAP applications using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="9505e-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="9505e-119">In This Section</span></span>  
  
-   [<span data-ttu-id="9505e-120">适配器如何连接到 SAP 系统？</span><span class="sxs-lookup"><span data-stu-id="9505e-120">How Does the Adapter Connect to an SAP System?</span></span>](https://msdn.microsoft.com/library/cc185540.aspx)  
  
-   [<span data-ttu-id="9505e-121">原理适配器图面上的 SAP 元数据是什么？</span><span class="sxs-lookup"><span data-stu-id="9505e-121">How Does the Adapter Surface SAP Metadata?</span></span>](https://msdn.microsoft.com/library/dd788039.aspx)  
  
-   [<span data-ttu-id="9505e-122">哪些操作可以是执行使用适配器？</span><span class="sxs-lookup"><span data-stu-id="9505e-122">What Operations Can be Performed Using the Adapter?</span></span>](https://msdn.microsoft.com/library/dd788159.aspx)  
  
-   [<span data-ttu-id="9505e-123">适配器支持的其他功能</span><span class="sxs-lookup"><span data-stu-id="9505e-123">Other Features Supported by the Adapter</span></span>](https://msdn.microsoft.com/library/dd788022.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="9505e-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="9505e-124">See Also</span></span>  
 [<span data-ttu-id="9505e-125">了解用于 mySAP Business Suite 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="9505e-125">Understand BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)