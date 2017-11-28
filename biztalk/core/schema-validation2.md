---
title: "架构 Validation2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2f9d1576-10df-4c5a-9ae0-618f0dd54b4e
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 317fa8e0e5e557993922bba383ebf5eca460fa69
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="schema-validation"></a><span data-ttu-id="f4953-102">架构验证</span><span class="sxs-lookup"><span data-stu-id="f4953-102">Schema Validation</span></span>
<span data-ttu-id="f4953-103">EDI 接收管道和 EDI 发送管道使用以下架构对消息进行验证：</span><span class="sxs-lookup"><span data-stu-id="f4953-103">The EDI receive pipeline and EDI send pipeline validate a message using the following schemas:</span></span>  
  
-   <span data-ttu-id="f4953-104">**信封验证**： 服务架构中`Microsoft.BizTalk.Edi.BaseArtifacts.dll`中[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4953-104">**Envelope validation**: Service schema in `Microsoft.BizTalk.Edi.BaseArtifacts.dll` in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]</span></span>  
  
-   <span data-ttu-id="f4953-105">**事务集验证**： 架构中的消息架构将存储在[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI</span><span class="sxs-lookup"><span data-stu-id="f4953-105">**Transaction set validation**: Message schemas in the schema store in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI</span></span>  
  
-   <span data-ttu-id="f4953-106">**确认消息验证**: CONTRL，997 和中的 TA1 架构`Microsoft.BizTalk.Edi.BaseArtifacts.dll`。</span><span class="sxs-lookup"><span data-stu-id="f4953-106">**Acknowledgment message validation**: CONTRL, 997, and TA1 schema in `Microsoft.BizTalk.Edi.BaseArtifacts.dll`.</span></span>  
  
 <span data-ttu-id="f4953-107">`Microsoft.BizTalk.Edi.BaseArtifacts.dll` 中的架构由安装程序自动部署。</span><span class="sxs-lookup"><span data-stu-id="f4953-107">The schemas in `Microsoft.BizTalk.Edi.BaseArtifacts.dll` are automatically deployed by the setup program.</span></span> <span data-ttu-id="f4953-108">中列出了这些架构**架构**节点**BizTalk EDI 应用程序**中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="f4953-108">These schemas are listed in the **Schemas** node of the **BizTalk EDI Application** in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="f4953-109">若要使用消息架构，您必须通过执行 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI 文件夹中的 MicrosoftEdiXSDTemplates.exe 自解压缩文件，将消息架构安装在服务器的硬盘上，然后将其部署在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的项目中。</span><span class="sxs-lookup"><span data-stu-id="f4953-109">To use the message schemas, you must install them on the hard drive of your server by executing the MicrosoftEdiXSDTemplates.exe self-extracting file in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI folder, and then deploy them in your project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
 <span data-ttu-id="f4953-110">**架构确定**</span><span class="sxs-lookup"><span data-stu-id="f4953-110">**Schema Determination**</span></span>  
  
 <span data-ttu-id="f4953-111">当 EDI 接收管道处理接收消息时，它会通过协议查找和架构发现进程来确定处理该消息时要使用的架构的命名空间。</span><span class="sxs-lookup"><span data-stu-id="f4953-111">When the EDI receive pipeline processes a receive message, it determines the namespace of the schema to use in processing the message through the agreement lookup and schema discovery process.</span></span> <span data-ttu-id="f4953-112">有关详细信息，请参阅[协议解析、 架构发现和接收 EDI 消息的授权](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)。</span><span class="sxs-lookup"><span data-stu-id="f4953-112">For more information, see [Agreement Resolution, Schema Discovery, and Authorization for Received EDI Messages](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md).</span></span>  
  
 <span data-ttu-id="f4953-113">当 EDI 发送管道创建要发送的消息时，它会使用协议属性填充信封，然后对事务集中的信息进行架构验证。</span><span class="sxs-lookup"><span data-stu-id="f4953-113">When the EDI send pipeline creates a message to send, it uses agreement properties to populate the envelope, and then performs schema validation of the information in the transaction set.</span></span> <span data-ttu-id="f4953-114">加载架构之后，发送管道会根据协议属性对架构进行验证（如果未指定任何协议，则根据后备协议进行验证）。</span><span class="sxs-lookup"><span data-stu-id="f4953-114">After loading the schema, the send pipeline validates the schema against agreement properties (or fallback agreement if no agreement has been designated).</span></span> <span data-ttu-id="f4953-115">如果架构验证通过，管道会根据该架构对事务集进行验证。</span><span class="sxs-lookup"><span data-stu-id="f4953-115">If the schema validates, the pipeline validates the transaction set against the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4953-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f4953-116">See Also</span></span>  
 [<span data-ttu-id="f4953-117">EDI 消息验证</span><span class="sxs-lookup"><span data-stu-id="f4953-117">EDI Message Validation</span></span>](../core/edi-message-validation.md)