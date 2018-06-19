---
title: 如何在业务流程中使用地图 |Microsoft 文档
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
ms.openlocfilehash: e67249857ec00b2ca66648c1985f0c336d93b3b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255325"
---
# <a name="how-to-use-maps-in-orchestrations"></a><span data-ttu-id="970ef-102">如何在业务流程中使用地图</span><span class="sxs-lookup"><span data-stu-id="970ef-102">How to Use Maps in Orchestrations</span></span>
<span data-ttu-id="970ef-103">BizTalk 映射程序是一个工具，在 Microsoft 内运行[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="970ef-103">BizTalk Mapper is a tool that runs within the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="970ef-104">BizTalk 映射器可用来创建和编辑映射，在映射中可使用链接和 functoid 定义输入和输出架构之间的关系。</span><span class="sxs-lookup"><span data-stu-id="970ef-104">You use BizTalk Mapper to create and edit maps in which you use links and functoids to define the relationship between an input and an output schema.</span></span> <span data-ttu-id="970ef-105">链接定义了记录或字段的直接数据复制。</span><span class="sxs-lookup"><span data-stu-id="970ef-105">A link defines a direct data copy of a record or field.</span></span> <span data-ttu-id="970ef-106">链接可以直接连接到另一架构中的项，也可以构成指向 functoid 的连接。</span><span class="sxs-lookup"><span data-stu-id="970ef-106">Links may directly connect to items in the other schema, or they may form connections to functoids.</span></span> <span data-ttu-id="970ef-107">functoid 可以执行更加复杂的数据操作。</span><span class="sxs-lookup"><span data-stu-id="970ef-107">Functoids perform more complex data manipulations.</span></span>  
  
## <a name="examples-of-using-maps"></a><span data-ttu-id="970ef-108">使用映射的示例</span><span class="sxs-lookup"><span data-stu-id="970ef-108">Examples of Using Maps</span></span>  
 <span data-ttu-id="970ef-109">下面的示例显示了几种映射的使用方法：</span><span class="sxs-lookup"><span data-stu-id="970ef-109">The following samples show ways in which you can use maps:</span></span>  
  
-   [<span data-ttu-id="970ef-110">XML 工具 （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="970ef-110">XML Tools (BizTalk Server Samples Folder)</span></span>](../core/xml-tools-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="970ef-111">PartyResolution （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="970ef-111">PartyResolution (BizTalk Server Sample)</span></span>](../core/partyresolution-biztalk-server-sample.md)  
  
-   <span data-ttu-id="970ef-112">从下载 SDK 示例"使用大容量复制 Functoid" [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="970ef-112">Download the SDK sample "Using the Mass Copy Functoid" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="970ef-113">从下载 SDK 示例"使用循环 Functoid" [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="970ef-113">Download the SDK sample "Using the Looping Functoid" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="970ef-114">从下载"映射到重复结构"中的 SDK 示例[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="970ef-114">Download the SDK sample "Mapping to a Repeating Structure" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="970ef-115">从下载 SDK 示例"使用表循环 Functoid" [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="970ef-115">Download the SDK sample "Using the Table Looping Functoid" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="970ef-116">从下载"使用的值映射和值映射 （平展） Functoid"SDK 示例[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="970ef-116">Download the SDK sample "Using the Value Mapping and Value Mapping (Flattening) Functoids" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="970ef-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="970ef-117">See Also</span></span>  
 <span data-ttu-id="970ef-118">[创建使用 BizTalk 映射程序图](../core/creating-maps-using-biztalk-mapper.md) </span><span class="sxs-lookup"><span data-stu-id="970ef-118">[Creating Maps Using BizTalk Mapper](../core/creating-maps-using-biztalk-mapper.md) </span></span>  
 <span data-ttu-id="970ef-119">[构造消息](../core/constructing-messages.md) </span><span class="sxs-lookup"><span data-stu-id="970ef-119">[Constructing Messages](../core/constructing-messages.md) </span></span>  
 <span data-ttu-id="970ef-120">[如何配置转换形状](../core/how-to-configure-the-transform-shape.md) </span><span class="sxs-lookup"><span data-stu-id="970ef-120">[How to Configure the Transform Shape](../core/how-to-configure-the-transform-shape.md) </span></span>  
 [<span data-ttu-id="970ef-121">如何使用动态转换消息的表达式</span><span class="sxs-lookup"><span data-stu-id="970ef-121">How to Use Expressions to Dynamic Transform Messages</span></span>](../core/how-to-use-expressions-to-dynamic-transform-messages.md)