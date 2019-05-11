---
title: 如何在业务流程中使用映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dfd628d8-c163-431d-8ad7-d7d77007c549
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 879b7a79db342ba7057cc4ff7a10efcf3c97fb62
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333442"
---
# <a name="how-to-use-maps-in-orchestrations"></a><span data-ttu-id="ed4c1-102">如何在业务流程中使用映射</span><span class="sxs-lookup"><span data-stu-id="ed4c1-102">How to Use Maps in Orchestrations</span></span>
<span data-ttu-id="ed4c1-103">BizTalk 映射程序是一个工具，在 Microsoft 内运行[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="ed4c1-103">BizTalk Mapper is a tool that runs within the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="ed4c1-104">使用 BizTalk 映射器创建和编辑的映射中用于链接和 functoid 定义输入和输出架构之间的关系。</span><span class="sxs-lookup"><span data-stu-id="ed4c1-104">You use BizTalk Mapper to create and edit maps in which you use links and functoids to define the relationship between an input and an output schema.</span></span> <span data-ttu-id="ed4c1-105">链接定义记录或字段的直接数据的复制。</span><span class="sxs-lookup"><span data-stu-id="ed4c1-105">A link defines a direct data copy of a record or field.</span></span> <span data-ttu-id="ed4c1-106">链接可以直接连接到其他架构中的项或也可以构成指向 functoid 的连接。</span><span class="sxs-lookup"><span data-stu-id="ed4c1-106">Links may directly connect to items in the other schema, or they may form connections to functoids.</span></span> <span data-ttu-id="ed4c1-107">Functoid 可以执行更复杂的数据操作。</span><span class="sxs-lookup"><span data-stu-id="ed4c1-107">Functoids perform more complex data manipulations.</span></span>  
  
## <a name="examples-of-using-maps"></a><span data-ttu-id="ed4c1-108">使用映射的示例</span><span class="sxs-lookup"><span data-stu-id="ed4c1-108">Examples of Using Maps</span></span>  
 <span data-ttu-id="ed4c1-109">下面的示例演示了你可以在其中使用映射的方式：</span><span class="sxs-lookup"><span data-stu-id="ed4c1-109">The following samples show ways in which you can use maps:</span></span>  
  
-   [<span data-ttu-id="ed4c1-110">XML 工具（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="ed4c1-110">XML Tools (BizTalk Server Samples Folder)</span></span>](../core/xml-tools-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="ed4c1-111">PartyResolution（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="ed4c1-111">PartyResolution (BizTalk Server Sample)</span></span>](../core/partyresolution-biztalk-server-sample.md)  
  
-   <span data-ttu-id="ed4c1-112">从下载 SDK 示例"使用大容量复制 Functoid" [ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="ed4c1-112">Download the SDK sample "Using the Mass Copy Functoid" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="ed4c1-113">从下载 SDK 示例"使用循环 Functoid" [ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="ed4c1-113">Download the SDK sample "Using the Looping Functoid" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="ed4c1-114">从下载 SDK 示例"映射到重复结构" [ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="ed4c1-114">Download the SDK sample "Mapping to a Repeating Structure" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="ed4c1-115">从下载 SDK 示例"使用表循环 ' Functoid" [ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="ed4c1-115">Download the SDK sample "Using the Table Looping Functoid" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="ed4c1-116">从下载 SDK 示例"使用的值映射和值映射 （平展） Functoid" [ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="ed4c1-116">Download the SDK sample "Using the Value Mapping and Value Mapping (Flattening) Functoids" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed4c1-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed4c1-117">See Also</span></span>  
 <span data-ttu-id="ed4c1-118">[使用 BizTalk 映射器创建映射](../core/creating-maps-using-biztalk-mapper.md) </span><span class="sxs-lookup"><span data-stu-id="ed4c1-118">[Creating Maps Using BizTalk Mapper](../core/creating-maps-using-biztalk-mapper.md) </span></span>  
 <span data-ttu-id="ed4c1-119">[构造消息](../core/constructing-messages.md) </span><span class="sxs-lookup"><span data-stu-id="ed4c1-119">[Constructing Messages](../core/constructing-messages.md) </span></span>  
 <span data-ttu-id="ed4c1-120">[如何配置转换形状](../core/how-to-configure-the-transform-shape.md) </span><span class="sxs-lookup"><span data-stu-id="ed4c1-120">[How to Configure the Transform Shape](../core/how-to-configure-the-transform-shape.md) </span></span>  
 [<span data-ttu-id="ed4c1-121">如何使用表达式来动态转换消息</span><span class="sxs-lookup"><span data-stu-id="ed4c1-121">How to Use Expressions to Dynamic Transform Messages</span></span>](../core/how-to-use-expressions-to-dynamic-transform-messages.md)