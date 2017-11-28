---
title: "更新 2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 770c9ebb-df3a-428f-be18-b36535352f8d
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4376cae94e91f462974c626a57170b80b0117ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="update"></a><span data-ttu-id="1f542-102">Update</span><span class="sxs-lookup"><span data-stu-id="1f542-102">Update</span></span>
<span data-ttu-id="1f542-103">`Update`元素用来从事件中提取数据并将其导入相关的 BAM 活动。</span><span class="sxs-lookup"><span data-stu-id="1f542-103">The `Update` element is used to extract data from an event and import it into the related BAM activity.</span></span>  
  
## <a name="format"></a><span data-ttu-id="1f542-104">格式</span><span class="sxs-lookup"><span data-stu-id="1f542-104">Format</span></span>  
 <span data-ttu-id="1f542-105">若要使用`Update`元素，你必须提供两个列名称和类型和**表达式**元素，其中包含一个或多个**操作**计算结果为单个字符串值的元素。</span><span class="sxs-lookup"><span data-stu-id="1f542-105">To use the `Update` element, you must provide both a column name and type and an **Expression** element containing one or more **Operation** elements that evaluate to a single string value.</span></span>  
  
```  
<ic:Update DataItemName="Name" Type="Type">  
  <ic:Expression>  
    <!-- one or more Operation elements -->  
  </ic:Expression>  
</ic:Update>  
```  
  
### <a name="attributes"></a><span data-ttu-id="1f542-106">属性</span><span class="sxs-lookup"><span data-stu-id="1f542-106">Attributes</span></span>  
  
|<span data-ttu-id="1f542-107">属性名称</span><span class="sxs-lookup"><span data-stu-id="1f542-107">Attribute name</span></span>|<span data-ttu-id="1f542-108">Description</span><span class="sxs-lookup"><span data-stu-id="1f542-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="1f542-109">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1f542-109">ColumnName</span></span>|<span data-ttu-id="1f542-110">BAM 活动检查点名称。</span><span class="sxs-lookup"><span data-stu-id="1f542-110">BAM activity checkpoint name.</span></span> <span data-ttu-id="1f542-111">将使用提取的数据对该检查点进行更新。</span><span class="sxs-lookup"><span data-stu-id="1f542-111">This is the checkpoint that will be updated with the extracted data.</span></span>|  
|<span data-ttu-id="1f542-112">类型</span><span class="sxs-lookup"><span data-stu-id="1f542-112">Type</span></span>|<span data-ttu-id="1f542-113">检查点的 BAM 数据类型；它必须是以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="1f542-113">BAM data type of the checkpoint; must be one of the following:</span></span><br /><br /> <span data-ttu-id="1f542-114">-NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="1f542-114">-   NVARCHAR</span></span><br /><span data-ttu-id="1f542-115">-DATETIME</span><span class="sxs-lookup"><span data-stu-id="1f542-115">-   DATETIME</span></span><br /><span data-ttu-id="1f542-116">INT</span><span class="sxs-lookup"><span data-stu-id="1f542-116">-   INT</span></span><br /><span data-ttu-id="1f542-117">浮点型</span><span class="sxs-lookup"><span data-stu-id="1f542-117">-   FLOAT</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f542-118">注释</span><span class="sxs-lookup"><span data-stu-id="1f542-118">Remarks</span></span>  
 <span data-ttu-id="1f542-119">中不支持以下操作`Update`表达式：</span><span class="sxs-lookup"><span data-stu-id="1f542-119">The following operations are not supported in the `Update` expression:</span></span>  
  
-   <span data-ttu-id="1f542-120">And</span><span class="sxs-lookup"><span data-stu-id="1f542-120">And</span></span>  
  
-   <span data-ttu-id="1f542-121">等于</span><span class="sxs-lookup"><span data-stu-id="1f542-121">Equals</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f542-122">示例</span><span class="sxs-lookup"><span data-stu-id="1f542-122">Example</span></span>  
 <span data-ttu-id="1f542-123">在下面的示例中， **GetContextProperty** WF 操作用于检索**EventTime**属性。</span><span class="sxs-lookup"><span data-stu-id="1f542-123">In the following example, the **GetContextProperty** WF operation is used to retrieve the **EventTime** property.</span></span> <span data-ttu-id="1f542-124">此值将存储为**DATETIME** BAM 活动的"StartOrderProcessing"数据项目类型。</span><span class="sxs-lookup"><span data-stu-id="1f542-124">This value will be stored as a **DATETIME** type for the "StartOrderProcessing" data item for the BAM activity.</span></span>  
  
```  
<ic:Update DataItemName="StartOrderProcessing" Type="DATETIME">  
  <ic:Expression>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>EventTime</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:Update>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1f542-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f542-125">See Also</span></span>  
 [<span data-ttu-id="1f542-126">拦截器 OnEvent 元素</span><span class="sxs-lookup"><span data-stu-id="1f542-126">Interceptor OnEvent Element</span></span>](../core/interceptor-onevent-element.md)