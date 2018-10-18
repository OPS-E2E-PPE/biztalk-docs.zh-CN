---
title: 重新提交说明和限制 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 391064a9-1d61-4b10-97ab-d93b37d1ae23
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d03c969dc056e251d8109ce5bc0a29c16f8ffeda
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976603"
---
# <a name="resubmission-notes-and-restrictions"></a><span data-ttu-id="a9cd9-102">重新提交说明和限制</span><span class="sxs-lookup"><span data-stu-id="a9cd9-102">Resubmission Notes and Restrictions</span></span>
<span data-ttu-id="a9cd9-103">下面的注意事项和限制适用于重新提交过程：</span><span class="sxs-lookup"><span data-stu-id="a9cd9-103">The following notes and restrictions apply to the resubmission process:</span></span>  
  
-   <span data-ttu-id="a9cd9-104">你可以重新提交到 ESB WCF 的负载增加，SOAP (ASMX) 上的负载增加，XML 消息或任何 HTTP 接收位置。</span><span class="sxs-lookup"><span data-stu-id="a9cd9-104">You can resubmit XML messages to the ESB WCF on-ramp, SOAP (ASMX) on-ramp, or any HTTP receive location.</span></span>  
  
-   <span data-ttu-id="a9cd9-105">用于在提升 WCF 默认 URL 为 http://localhost/ESB.ItineraryServices.WCF/ProcessItinerary.svc。</span><span class="sxs-lookup"><span data-stu-id="a9cd9-105">The default URL for the WCF on-ramp is http://localhost/ESB.ItineraryServices.WCF/ProcessItinerary.svc.</span></span>  
  
-   <span data-ttu-id="a9cd9-106">门户网站的 Web.config 文件定义 WCF 入口中的终结点详细信息**\<客户端\>** 节点**\<System.ServiceModel\>** 部分。</span><span class="sxs-lookup"><span data-stu-id="a9cd9-106">The portal Web.config file defines the endpoint details for the WCF on-ramp in the **\<Client\>** node of the **\<System.ServiceModel\>** section.</span></span> <span data-ttu-id="a9cd9-107">下面是默认值。</span><span class="sxs-lookup"><span data-stu-id="a9cd9-107">The following is the default value.</span></span>  
  
    ```  
    <endpoint  
      address="http://localhost/ESB.ItineraryServices.WCF/ProcessItinerary.svc"  
      binding="wsHttpBinding"  
      bindingConfiguration="WSHttpBinding_ITwoWayAsyncVoid"  
      contract="ProcessRequest"   
      name="WSHttpBinding_ITwoWayAsyncVoid">                  
    </endpoint>  
    ```  
  
-   <span data-ttu-id="a9cd9-108">如果上提升 WCF 驻留在远程服务器上，则必须更新以指向正确的服务器的地址。</span><span class="sxs-lookup"><span data-stu-id="a9cd9-108">If the WCF on-ramp resides on a remote server, you must update the address to point to the correct server.</span></span>  
  
-   <span data-ttu-id="a9cd9-109">用于在提升 SOAP (ASMX) 默认 URL 为 http://localhost/ESB.ItineraryServices/ProcessItinerary.asmx。</span><span class="sxs-lookup"><span data-stu-id="a9cd9-109">The default URL for the SOAP (ASMX) on-ramp is http://localhost/ESB.ItineraryServices/ProcessItinerary.asmx.</span></span>  
  
-   <span data-ttu-id="a9cd9-110">门户网站的 Web.config 文件定义的 SOAP (ASMX) 上的负载增加中配置**\<applicationSettings\>** 部分。</span><span class="sxs-lookup"><span data-stu-id="a9cd9-110">The portal Web.config file defines the configuration for the SOAP (ASMX) on-ramp in the **\<applicationSettings\>** section.</span></span> <span data-ttu-id="a9cd9-111">下面是默认值。</span><span class="sxs-lookup"><span data-stu-id="a9cd9-111">The following is the default value.</span></span>  
  
    ```  
    <setting   
      name="Microsoft_Practices_ESB_Portal_ProcessItinerary_Process"  
      serializeAs="String">  
      <value>  
        http://localhost/ESB.ItineraryServices/ProcessItinerary.asmx  
      </value>  
    </setting>  
    ```  
  
-   <span data-ttu-id="a9cd9-112">如果上提升 ASMX 驻留在远程服务器上，你需要将 URL 更新具有正确的服务器地址。</span><span class="sxs-lookup"><span data-stu-id="a9cd9-112">If the ASMX on-ramp resides on a remote server, you need to update the URL with the correct server address.</span></span>  
  
-   <span data-ttu-id="a9cd9-113">你可以重新提交平面文件格式的消息，仅对 HTTP 接收位置。</span><span class="sxs-lookup"><span data-stu-id="a9cd9-113">You can resubmit flat file formatted messages only to an HTTP receive location.</span></span> <span data-ttu-id="a9cd9-114">无法将其提交至 WCF 或 SOAP 入口。</span><span class="sxs-lookup"><span data-stu-id="a9cd9-114">You cannot submit them to a WCF or SOAP on-ramp.</span></span> <span data-ttu-id="a9cd9-115">你必须确保 HTTP 接收位置具有相应的管道，可以使用和/或分析平面文件。</span><span class="sxs-lookup"><span data-stu-id="a9cd9-115">You must ensure that the HTTP receive location has the appropriate pipeline that can consume and/or parse the flat file.</span></span>  
  
-   <span data-ttu-id="a9cd9-116">重新提交的消息不包含任何原始消息的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="a9cd9-116">The resubmitted message does not contain any of the context properties of the original message.</span></span>  
  
-   <span data-ttu-id="a9cd9-117">重新提交适用于仅消息正文;它不适用于整个消息。</span><span class="sxs-lookup"><span data-stu-id="a9cd9-117">Resubmission applies to only the message body; it does not apply to the entire message.</span></span>  
  
-   <span data-ttu-id="a9cd9-118">重新提交过程支持仅单一部分消息。</span><span class="sxs-lookup"><span data-stu-id="a9cd9-118">The resubmission process supports only single-part messages.</span></span> <span data-ttu-id="a9cd9-119">重新提交过程不能使用多个部分的消息。</span><span class="sxs-lookup"><span data-stu-id="a9cd9-119">You cannot use the resubmission process with multi-part messages.</span></span>  
  
-   <span data-ttu-id="a9cd9-120">你不能重新提交二进制格式的消息。</span><span class="sxs-lookup"><span data-stu-id="a9cd9-120">You cannot resubmit binary-formatted messages.</span></span>