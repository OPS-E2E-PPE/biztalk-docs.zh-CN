---
title: 生成 XSD 架构为 JSON 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5453b76c-b282-442f-9eb1-6c2628b38ad5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f44b18593e756fe1ed6e05e03d62e498f66c0a3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387763"
---
# <a name="generate-an-xsd-schema-for-json-message"></a><span data-ttu-id="6711b-102">生成 XSD 架构为 JSON 消息</span><span class="sxs-lookup"><span data-stu-id="6711b-102">Generate an XSD schema for JSON message</span></span>
> [!NOTE]
>  <span data-ttu-id="6711b-103">本教程仅适用于 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="6711b-103">This tutorial applies to BizTalk Server only.</span></span>  
  
 <span data-ttu-id="6711b-104">在此解决方案中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序接收 JSON 消息。</span><span class="sxs-lookup"><span data-stu-id="6711b-104">In this solution, a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application receives a JSON message.</span></span> <span data-ttu-id="6711b-105">应用程序能够处理该消息之前，它必须转换为 XSD 架构。</span><span class="sxs-lookup"><span data-stu-id="6711b-105">Before the application can process the message, it must be converted to an XSD schema.</span></span> <span data-ttu-id="6711b-106">为此，请[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供了从 JSON 消息创建 XSD 架构的 JSON 架构向导。</span><span class="sxs-lookup"><span data-stu-id="6711b-106">To do so, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides a JSON Schema Wizard that creates an XSD schema from a JSON message.</span></span>  
  
1. <span data-ttu-id="6711b-107">在 Visual Studio 中，创建一个新[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目。</span><span class="sxs-lookup"><span data-stu-id="6711b-107">In Visual Studio, create a new [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span>  
  
2. <span data-ttu-id="6711b-108">在解决方案资源管理器，右键单击项目名称 >**外** > **新项** > **JSON 架构向导**。</span><span class="sxs-lookup"><span data-stu-id="6711b-108">In the Solution Explorer, right-click the project name > **Add** > **New Item** > **JSON Schema Wizard**.</span></span> <span data-ttu-id="6711b-109">提供架构的名称 (`PO.xsd`)，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="6711b-109">Provide a name for the schema (`PO.xsd`), and then click **Add**.</span></span>  
  
3. <span data-ttu-id="6711b-110">在 JSON 架构向导中，在欢迎页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6711b-110">In the JSON Schema Wizard, on the welcome page, click **Next**.</span></span>  
  
4. <span data-ttu-id="6711b-111">在 JSON 架构信息页中提供的 JSON 采购订单文件发送到的位置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="6711b-111">In the JSON Schema Information page, provide the location of the JSON purchase order file that is sent to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span> <span data-ttu-id="6711b-112">提供根节点名、 目标命名空间，并单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="6711b-112">Provide a root node name, a target namespace, and then click **Finish**.</span></span>  
  
    <span data-ttu-id="6711b-113">![生成的 XSD 架构的 JSON](../core/media/btsjson-wizard.png "BTSJSON_Wizard")</span><span class="sxs-lookup"><span data-stu-id="6711b-113">![Generated XSD schema for JSON](../core/media/btsjson-wizard.png "BTSJSON_Wizard")</span></span>  
  
5. <span data-ttu-id="6711b-114">具有指定名称的架构添加到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目。</span><span class="sxs-lookup"><span data-stu-id="6711b-114">A schema with the specified name is added to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="6711b-115">生成的架构文件 (**PO.xsd**) 还提供的示例。</span><span class="sxs-lookup"><span data-stu-id="6711b-115">The generated schema file (**PO.xsd**) is also provided with the sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6711b-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="6711b-116">See Also</span></span>  
 [<span data-ttu-id="6711b-117">使用 BizTalk Server 处理 JSON 消息</span><span class="sxs-lookup"><span data-stu-id="6711b-117">Processing JSON messages using BizTalk Server</span></span>](../core/processing-json-messages-using-biztalk-server.md)