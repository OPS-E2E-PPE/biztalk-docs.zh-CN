---
title: 如何创建没有地图图 |Microsoft 文档
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
ms.openlocfilehash: 81be2591c1d8f20f5b8dd01cf01c03e8daed9c9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248789"
---
# <a name="how-to-create-a-map-without-maps"></a><span data-ttu-id="e7bfe-102">如何创建没有映射图</span><span class="sxs-lookup"><span data-stu-id="e7bfe-102">How to Create a Map without Maps</span></span>
<span data-ttu-id="e7bfe-103">如果具有已用于转换实例消息的 XSLT 代码，则可以直接使用该代码，而不用创建映射。</span><span class="sxs-lookup"><span data-stu-id="e7bfe-103">If you have XSLT code you have been using to convert instance messages, you can use that code directly instead of creating a map.</span></span>  
  
 <span data-ttu-id="e7bfe-104">使用 XSLT 代码需要创建一个空的映射，并设置其**自定义 XSLT 路径**网格属性。</span><span class="sxs-lookup"><span data-stu-id="e7bfe-104">Using your XSLT code involves creating an empty map and setting its **Custom XSLT Path** grid property.</span></span> <span data-ttu-id="e7bfe-105">如果 XSLT 代码使用外部.NET 程序集，你还需要创建一个自定义扩展的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="e7bfe-105">If your XSLT code uses external .NET assemblies, you also need to create a custom extension XML file.</span></span> <span data-ttu-id="e7bfe-106">有关自定义扩展的 XML 文件的结构的信息，请参阅**自定义扩展 XML （网格属性）** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="e7bfe-106">For information about the structure of a custom extension XML file, see the **Custom Extension XML (Grid Property)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="use-custom-xslt-code-in-place-of-a-map"></a><span data-ttu-id="e7bfe-107">使用自定义 XSLT 代码，以地图取代</span><span class="sxs-lookup"><span data-stu-id="e7bfe-107">Use custom XSLT code in place of a map</span></span>  
  
1.  <span data-ttu-id="e7bfe-108">在项目中创建空 BizTalk 映射，并设置源架构和目标架构。</span><span class="sxs-lookup"><span data-stu-id="e7bfe-108">Create an empty BizTalk map in your project and set the source and destination schemas.</span></span>  
  
     <span data-ttu-id="e7bfe-109">有关创建代码图和设置架构的信息，请参阅[创建地图](../core/creating-maps.md)。</span><span class="sxs-lookup"><span data-stu-id="e7bfe-109">For information about creating the map and setting the schemas, see [Creating Maps](../core/creating-maps.md).</span></span>  
  
2.  <span data-ttu-id="e7bfe-110">在网格视图中，单击映射器网格。</span><span class="sxs-lookup"><span data-stu-id="e7bfe-110">In the Grid view, click the mapper grid.</span></span>  
  
     <span data-ttu-id="e7bfe-111">属性窗口中显示**网格**属性。</span><span class="sxs-lookup"><span data-stu-id="e7bfe-111">The Properties window shows the **Grid** properties.</span></span>  
  
3.  <span data-ttu-id="e7bfe-112">在属性窗口中，选择**自定义 XSLT 路径**单击省略号 (**...**) 按钮。</span><span class="sxs-lookup"><span data-stu-id="e7bfe-112">In the Properties window, select **Custom XSLT Path** and click the ellipsis (**…**) button.</span></span>  
  
4.  <span data-ttu-id="e7bfe-113">在**打开**对话框框中，导航到该文件并单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="e7bfe-113">In the **Open** dialog box, navigate to the file and click **Open**.</span></span>  
  
     <span data-ttu-id="e7bfe-114">**自定义 XSLT 路径**属性设置。</span><span class="sxs-lookup"><span data-stu-id="e7bfe-114">The **Custom XSLT Path** property is set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7bfe-115">BizTalk 映射器仅支持 XSLT 1.0。</span><span class="sxs-lookup"><span data-stu-id="e7bfe-115">BizTalk Mapper supports XSLT 1.0 only.</span></span> <span data-ttu-id="e7bfe-116">不支持在 BizTalk 映射器中使用 XSLT 2.0。</span><span class="sxs-lookup"><span data-stu-id="e7bfe-116">Using XSLT 2.0 in BizTalk Mapper is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7bfe-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7bfe-117">See Also</span></span>  
 <span data-ttu-id="e7bfe-118">[有关映射](../core/about-maps.md) </span><span class="sxs-lookup"><span data-stu-id="e7bfe-118">[About Maps](../core/about-maps.md) </span></span>  
 <span data-ttu-id="e7bfe-119">[脚本使用内联 XSLT 和 XSLT 调用模板](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span><span class="sxs-lookup"><span data-stu-id="e7bfe-119">[Scripting Using Inline XSLT and XSLT Call Templates](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span></span>  
 [<span data-ttu-id="e7bfe-120">自定义 XSLT</span><span class="sxs-lookup"><span data-stu-id="e7bfe-120">Custom XSLT</span></span>](../core/custom-xslt.md)   