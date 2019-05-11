---
title: 架构 Validation2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f9d1576-10df-4c5a-9ae0-618f0dd54b4e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f74afc7c9b0a10c5050ce13d7ce5ab9c8c13967f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396873"
---
# <a name="schema-validation"></a><span data-ttu-id="61458-102">架构验证</span><span class="sxs-lookup"><span data-stu-id="61458-102">Schema Validation</span></span>
<span data-ttu-id="61458-103">EDI 接收管道和 EDI 发送管道验证使用以下架构的消息：</span><span class="sxs-lookup"><span data-stu-id="61458-103">The EDI receive pipeline and EDI send pipeline validate a message using the following schemas:</span></span>  
  
- <span data-ttu-id="61458-104">**信封验证**:服务架构`Microsoft.BizTalk.Edi.BaseArtifacts.dll`中 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61458-104">**Envelope validation**: Service schema in `Microsoft.BizTalk.Edi.BaseArtifacts.dll` in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]</span></span>  
  
- <span data-ttu-id="61458-105">**事务集验证**:在架构中的消息架构将存储在[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI</span><span class="sxs-lookup"><span data-stu-id="61458-105">**Transaction set validation**: Message schemas in the schema store in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI</span></span>  
  
- <span data-ttu-id="61458-106">**确认消息验证**:CONTRL，997 和 TA1 架构中的`Microsoft.BizTalk.Edi.BaseArtifacts.dll`。</span><span class="sxs-lookup"><span data-stu-id="61458-106">**Acknowledgment message validation**: CONTRL, 997, and TA1 schema in `Microsoft.BizTalk.Edi.BaseArtifacts.dll`.</span></span>  
  
  <span data-ttu-id="61458-107">中的架构`Microsoft.BizTalk.Edi.BaseArtifacts.dll`由安装程序自动部署。</span><span class="sxs-lookup"><span data-stu-id="61458-107">The schemas in `Microsoft.BizTalk.Edi.BaseArtifacts.dll` are automatically deployed by the setup program.</span></span> <span data-ttu-id="61458-108">这些架构所示**架构**的节点**BizTalk EDI 应用程序**中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="61458-108">These schemas are listed in the **Schemas** node of the **BizTalk EDI Application** in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
  <span data-ttu-id="61458-109">若要使用的消息架构，必须安装在你的服务器的硬盘驱动器上的执行中的 MicrosoftEdiXSDTemplates.exe 自解压缩文件[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI 文件夹中，然后将其部署在你的项目中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="61458-109">To use the message schemas, you must install them on the hard drive of your server by executing the MicrosoftEdiXSDTemplates.exe self-extracting file in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI folder, and then deploy them in your project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
  <span data-ttu-id="61458-110">**架构确定**</span><span class="sxs-lookup"><span data-stu-id="61458-110">**Schema Determination**</span></span>  
  
  <span data-ttu-id="61458-111">当 EDI 接收管道处理接收消息时，它确定要在通过协议查找和架构发现进程处理该消息中使用的架构的命名空间。</span><span class="sxs-lookup"><span data-stu-id="61458-111">When the EDI receive pipeline processes a receive message, it determines the namespace of the schema to use in processing the message through the agreement lookup and schema discovery process.</span></span> <span data-ttu-id="61458-112">有关详细信息，请参阅[协议解析、 架构发现和收到的 EDI 消息的授权](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)。</span><span class="sxs-lookup"><span data-stu-id="61458-112">For more information, see [Agreement Resolution, Schema Discovery, and Authorization for Received EDI Messages](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md).</span></span>  
  
  <span data-ttu-id="61458-113">当 EDI 发送管道创建要发送的消息时，它使用协议属性填充信封，然后事务集中执行架构验证的信息。</span><span class="sxs-lookup"><span data-stu-id="61458-113">When the EDI send pipeline creates a message to send, it uses agreement properties to populate the envelope, and then performs schema validation of the information in the transaction set.</span></span> <span data-ttu-id="61458-114">加载架构之后, 的发送管道验证对协议属性 （或如果已指定不存在的协议的后备协议） 的架构。</span><span class="sxs-lookup"><span data-stu-id="61458-114">After loading the schema, the send pipeline validates the schema against agreement properties (or fallback agreement if no agreement has been designated).</span></span> <span data-ttu-id="61458-115">如果架构验证通过，管道会验证的事务集根据架构。</span><span class="sxs-lookup"><span data-stu-id="61458-115">If the schema validates, the pipeline validates the transaction set against the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61458-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="61458-116">See Also</span></span>  
 [<span data-ttu-id="61458-117">EDI 消息验证</span><span class="sxs-lookup"><span data-stu-id="61458-117">EDI Message Validation</span></span>](../core/edi-message-validation.md)