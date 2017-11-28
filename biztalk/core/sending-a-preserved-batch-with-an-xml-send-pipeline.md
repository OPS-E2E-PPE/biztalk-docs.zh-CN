---
title: "发送带有 XML 的保留批次发送管道 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6765576a-134f-4856-911c-2f603b6479bd
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14bd61538398bb11967cbbe750a4fadc016a5168
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sending-a-preserved-batch-with-an-xml-send-pipeline"></a><span data-ttu-id="7d5da-102">使用 XML 发送管道发送保留批</span><span class="sxs-lookup"><span data-stu-id="7d5da-102">Sending a Preserved Batch with an XML Send Pipeline</span></span>
<span data-ttu-id="7d5da-103">通常，使用 EDI 发送管道发送保留批。</span><span class="sxs-lookup"><span data-stu-id="7d5da-103">Normally, a preserved batch is sent using an EDI send pipeline.</span></span> <span data-ttu-id="7d5da-104">但是，也可以使用 XML 发送管道发送保留批。</span><span class="sxs-lookup"><span data-stu-id="7d5da-104">However, you can also use an XML send pipeline to send a preserved batch.</span></span> <span data-ttu-id="7d5da-105">因为由 EDI 接收管道生成并放置在 MessageBox 中的保留批是 XML 格式的，XML 发送管道将以 XML 格式传递批。</span><span class="sxs-lookup"><span data-stu-id="7d5da-105">Since the preserved batch that is generated and dropped in the MessageBox by the EDI receive pipeline is in the XML format, the XML send pipeline would pass along the batch in XML format.</span></span>  
  
 <span data-ttu-id="7d5da-106">若要使用 XML 发送管道发送保留批，必须部署一个项目，同时为交换中的每种消息类型设置适用的批架构和文档架构。</span><span class="sxs-lookup"><span data-stu-id="7d5da-106">To send a preserved batch using the XML send pipeline, you have to deploy a project with the applicable batch schema and the document schemas for each message type in the interchange.</span></span> <span data-ttu-id="7d5da-107">此外，还必须更改要在项目中部署的批架构的命名空间。</span><span class="sxs-lookup"><span data-stu-id="7d5da-107">In addition, you also have to change the namespace for the batch schema that you deploy in the project.</span></span> <span data-ttu-id="7d5da-108">如果不这样做，保留批 XML 文件中的命名空间将与批架构的命名空间不相符。</span><span class="sxs-lookup"><span data-stu-id="7d5da-108">If you do not do so, the namespace in the preserved batch XML file would not correspond to the namespace for the batch schema.</span></span> <span data-ttu-id="7d5da-109">您必须按照下表所示，更改批架构的命名空间：</span><span class="sxs-lookup"><span data-stu-id="7d5da-109">You have to change the namespace for the batch schema as shown in the following table:</span></span>  
  
|<span data-ttu-id="7d5da-110">对于此编码类型：</span><span class="sxs-lookup"><span data-stu-id="7d5da-110">For this encoding type:</span></span>|<span data-ttu-id="7d5da-111">更改批架构中的此命名空间：</span><span class="sxs-lookup"><span data-stu-id="7d5da-111">Change this namespace in the batch schema:</span></span>|<span data-ttu-id="7d5da-112">更改为以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="7d5da-112">To the following namespace:</span></span>|  
|-----------------------------|------------------------------------------------|---------------------------------|  
|<span data-ttu-id="7d5da-113">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="7d5da-113">EDIFACT</span></span>|`http://schemas.microsoft.com/Edi/Edifact`|`http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006/InterchangeXML`|  
|<span data-ttu-id="7d5da-114">X12</span><span class="sxs-lookup"><span data-stu-id="7d5da-114">X12</span></span>|`http://schemas.microsoft.com/Edi/X12_BatchSchema`|`http://schemas.microsoft.com/BizTalk/EDI/X12/2006/InterchangeXML`|  
  
 <span data-ttu-id="7d5da-115">对于 EDI 组装器不存在此问题。</span><span class="sxs-lookup"><span data-stu-id="7d5da-115">This is not an issue with the EDI Assembler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d5da-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d5da-116">See Also</span></span>  
 [<span data-ttu-id="7d5da-117">配置 EDI 批处理</span><span class="sxs-lookup"><span data-stu-id="7d5da-117">Configuring EDI Batches</span></span>](../core/configuring-edi-batches.md)