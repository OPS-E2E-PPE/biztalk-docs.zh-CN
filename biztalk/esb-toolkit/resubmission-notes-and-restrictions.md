---
title: 重新提交说明和限制 |Microsoft Docs
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
ms.openlocfilehash: f08f6a2740331518d6fc92fb0c12e6f89d1b79f0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401506"
---
# <a name="resubmission-notes-and-restrictions"></a><span data-ttu-id="a976a-102">重新提交说明和限制</span><span class="sxs-lookup"><span data-stu-id="a976a-102">Resubmission Notes and Restrictions</span></span>
<span data-ttu-id="a976a-103">下面的注意事项和限制适用于重新提交过程：</span><span class="sxs-lookup"><span data-stu-id="a976a-103">The following notes and restrictions apply to the resubmission process:</span></span>  
  
-   <span data-ttu-id="a976a-104">您可以重新提交到了 ESB WCF 的途径，SOAP (ASMX) 的途径，XML 消息或任何 HTTP 接收位置。</span><span class="sxs-lookup"><span data-stu-id="a976a-104">You can resubmit XML messages to the ESB WCF on-ramp, SOAP (ASMX) on-ramp, or any HTTP receive location.</span></span>  
  
-   <span data-ttu-id="a976a-105">默认 url 为 WCF 帮手 http://localhost/ESB.ItineraryServices.WCF/ProcessItinerary.svc。</span><span class="sxs-lookup"><span data-stu-id="a976a-105">The default URL for the WCF on-ramp is http://localhost/ESB.ItineraryServices.WCF/ProcessItinerary.svc.</span></span>  
  
-   <span data-ttu-id="a976a-106">门户网站的 Web.config 文件定义了 WCF 的途径，在终结点详细信息 **\<客户端\>** 节点的 **\<System.ServiceModel\>** 部分。</span><span class="sxs-lookup"><span data-stu-id="a976a-106">The portal Web.config file defines the endpoint details for the WCF on-ramp in the **\<Client\>** node of the **\<System.ServiceModel\>** section.</span></span> <span data-ttu-id="a976a-107">以下是默认值。</span><span class="sxs-lookup"><span data-stu-id="a976a-107">The following is the default value.</span></span>  
  
    ```  
    <endpoint  
      address="http://localhost/ESB.ItineraryServices.WCF/ProcessItinerary.svc"  
      binding="wsHttpBinding"  
      bindingConfiguration="WSHttpBinding_ITwoWayAsyncVoid"  
      contract="ProcessRequest"   
      name="WSHttpBinding_ITwoWayAsyncVoid">                  
    </endpoint>  
    ```  
  
-   <span data-ttu-id="a976a-108">如果 WCF 帮手驻留在远程服务器上，则必须更新为指向正确的服务器的地址。</span><span class="sxs-lookup"><span data-stu-id="a976a-108">If the WCF on-ramp resides on a remote server, you must update the address to point to the correct server.</span></span>  
  
-   <span data-ttu-id="a976a-109">SOAP (ASMX) 接入点的默认 URL 是 http://localhost/ESB.ItineraryServices/ProcessItinerary.asmx。</span><span class="sxs-lookup"><span data-stu-id="a976a-109">The default URL for the SOAP (ASMX) on-ramp is http://localhost/ESB.ItineraryServices/ProcessItinerary.asmx.</span></span>  
  
-   <span data-ttu-id="a976a-110">门户网站的 Web.config 文件定义了 SOAP (ASMX) 的途径中的配置 **\<applicationSettings\>** 部分。</span><span class="sxs-lookup"><span data-stu-id="a976a-110">The portal Web.config file defines the configuration for the SOAP (ASMX) on-ramp in the **\<applicationSettings\>** section.</span></span> <span data-ttu-id="a976a-111">以下是默认值。</span><span class="sxs-lookup"><span data-stu-id="a976a-111">The following is the default value.</span></span>  
  
    ```  
    <setting   
      name="Microsoft_Practices_ESB_Portal_ProcessItinerary_Process"  
      serializeAs="String">  
      <value>  
        http://localhost/ESB.ItineraryServices/ProcessItinerary.asmx  
      </value>  
    </setting>  
    ```  
  
-   <span data-ttu-id="a976a-112">如果 ASMX 帮手驻留在远程服务器上，您需要使用正确的服务器地址更新 URL。</span><span class="sxs-lookup"><span data-stu-id="a976a-112">If the ASMX on-ramp resides on a remote server, you need to update the URL with the correct server address.</span></span>  
  
-   <span data-ttu-id="a976a-113">您可以重新提交平面文件格式的消息，仅对 HTTP 接收位置。</span><span class="sxs-lookup"><span data-stu-id="a976a-113">You can resubmit flat file formatted messages only to an HTTP receive location.</span></span> <span data-ttu-id="a976a-114">不能将其提交到 WCF 或 SOAP 接入点。</span><span class="sxs-lookup"><span data-stu-id="a976a-114">You cannot submit them to a WCF or SOAP on-ramp.</span></span> <span data-ttu-id="a976a-115">必须确保 HTTP 接收位置具有相应的管道，可以使用和/或分析平面文件。</span><span class="sxs-lookup"><span data-stu-id="a976a-115">You must ensure that the HTTP receive location has the appropriate pipeline that can consume and/or parse the flat file.</span></span>  
  
-   <span data-ttu-id="a976a-116">重新提交的消息不包含任何原始消息的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="a976a-116">The resubmitted message does not contain any of the context properties of the original message.</span></span>  
  
-   <span data-ttu-id="a976a-117">重新提交适用于只会将消息正文;它不适用于整个消息。</span><span class="sxs-lookup"><span data-stu-id="a976a-117">Resubmission applies to only the message body; it does not apply to the entire message.</span></span>  
  
-   <span data-ttu-id="a976a-118">重新提交过程支持仅单部分消息。</span><span class="sxs-lookup"><span data-stu-id="a976a-118">The resubmission process supports only single-part messages.</span></span> <span data-ttu-id="a976a-119">不能使用多部分消息重新提交过程。</span><span class="sxs-lookup"><span data-stu-id="a976a-119">You cannot use the resubmission process with multi-part messages.</span></span>  
  
-   <span data-ttu-id="a976a-120">无法重新提交二进制文件格式的邮件。</span><span class="sxs-lookup"><span data-stu-id="a976a-120">You cannot resubmit binary-formatted messages.</span></span>