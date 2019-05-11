---
title: 如何创建在无映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 520ec44f-5aca-4271-8835-b8e784214061
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c8d1ce3c42e1c776014036de7a832e8fd74b1be
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340040"
---
# <a name="how-to-create-a-map-without-maps"></a><span data-ttu-id="bd88b-102">如何创建在无映射</span><span class="sxs-lookup"><span data-stu-id="bd88b-102">How to Create a Map without Maps</span></span>
<span data-ttu-id="bd88b-103">如果您一直使用将实例消息的 XSLT 代码，您可以使用该代码直接而不是创建映射。</span><span class="sxs-lookup"><span data-stu-id="bd88b-103">If you have XSLT code you have been using to convert instance messages, you can use that code directly instead of creating a map.</span></span>  
  
 <span data-ttu-id="bd88b-104">使用 XSLT 代码时，需要创建空映射并设置其**自定义 XSLT 路径**网格属性。</span><span class="sxs-lookup"><span data-stu-id="bd88b-104">Using your XSLT code involves creating an empty map and setting its **Custom XSLT Path** grid property.</span></span> <span data-ttu-id="bd88b-105">如果 XSLT 代码使用外部.NET 程序集，还需要创建自定义扩展 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="bd88b-105">If your XSLT code uses external .NET assemblies, you also need to create a custom extension XML file.</span></span> <span data-ttu-id="bd88b-106">自定义扩展 XML 文件的结构有关的信息，请参阅**自定义扩展 XML （网格属性）** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="bd88b-106">For information about the structure of a custom extension XML file, see the **Custom Extension XML (Grid Property)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="use-custom-xslt-code-in-place-of-a-map"></a><span data-ttu-id="bd88b-107">使用自定义 XSLT 代码代替映射</span><span class="sxs-lookup"><span data-stu-id="bd88b-107">Use custom XSLT code in place of a map</span></span>  
  
1.  <span data-ttu-id="bd88b-108">在项目中创建空的 BizTalk 映射并设置源和目标架构。</span><span class="sxs-lookup"><span data-stu-id="bd88b-108">Create an empty BizTalk map in your project and set the source and destination schemas.</span></span>  
  
     <span data-ttu-id="bd88b-109">有关创建映射和设置架构的信息，请参阅[创建映射](../core/creating-maps.md)。</span><span class="sxs-lookup"><span data-stu-id="bd88b-109">For information about creating the map and setting the schemas, see [Creating Maps](../core/creating-maps.md).</span></span>  
  
2.  <span data-ttu-id="bd88b-110">在网格视图中，单击映射器网格。</span><span class="sxs-lookup"><span data-stu-id="bd88b-110">In the Grid view, click the mapper grid.</span></span>  
  
     <span data-ttu-id="bd88b-111">属性窗口显示**网格**属性。</span><span class="sxs-lookup"><span data-stu-id="bd88b-111">The Properties window shows the **Grid** properties.</span></span>  
  
3.  <span data-ttu-id="bd88b-112">在属性窗口中，选择**自定义 XSLT 路径**然后单击省略号 (**...**) 按钮。</span><span class="sxs-lookup"><span data-stu-id="bd88b-112">In the Properties window, select **Custom XSLT Path** and click the ellipsis (**…**) button.</span></span>  
  
4.  <span data-ttu-id="bd88b-113">在中**开放**对话框中，导航到该文件，单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="bd88b-113">In the **Open** dialog box, navigate to the file and click **Open**.</span></span>  
  
     <span data-ttu-id="bd88b-114">**自定义 XSLT 路径**属性设置。</span><span class="sxs-lookup"><span data-stu-id="bd88b-114">The **Custom XSLT Path** property is set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd88b-115">BizTalk 映射器仅支持 XSLT 1.0。</span><span class="sxs-lookup"><span data-stu-id="bd88b-115">BizTalk Mapper supports XSLT 1.0 only.</span></span> <span data-ttu-id="bd88b-116">不支持在 BizTalk 映射器中使用 XSLT 2.0。</span><span class="sxs-lookup"><span data-stu-id="bd88b-116">Using XSLT 2.0 in BizTalk Mapper is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd88b-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd88b-117">See Also</span></span>  
 <span data-ttu-id="bd88b-118">[有关地图](../core/about-maps.md) </span><span class="sxs-lookup"><span data-stu-id="bd88b-118">[About Maps](../core/about-maps.md) </span></span>  
 <span data-ttu-id="bd88b-119">[使用内联 XSLT 和 XSLT 调用模板编写脚本](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span><span class="sxs-lookup"><span data-stu-id="bd88b-119">[Scripting Using Inline XSLT and XSLT Call Templates](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span></span>  
 [<span data-ttu-id="bd88b-120">自定义 XSLT</span><span class="sxs-lookup"><span data-stu-id="bd88b-120">Custom XSLT</span></span>](../core/custom-xslt.md)   