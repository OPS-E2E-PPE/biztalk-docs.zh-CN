---
title: Update2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 770c9ebb-df3a-428f-be18-b36535352f8d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c090d11686babacfcb854782484b689dff2102e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398612"
---
# <a name="update"></a><span data-ttu-id="14e36-102">Update</span><span class="sxs-lookup"><span data-stu-id="14e36-102">Update</span></span>
<span data-ttu-id="14e36-103">`Update`元素用于从事件中提取数据并将其导入在相关 BAM 活动。</span><span class="sxs-lookup"><span data-stu-id="14e36-103">The `Update` element is used to extract data from an event and import it into the related BAM activity.</span></span>  
  
## <a name="format"></a><span data-ttu-id="14e36-104">格式</span><span class="sxs-lookup"><span data-stu-id="14e36-104">Format</span></span>  
 <span data-ttu-id="14e36-105">若要使用`Update`元素，你必须提供列名称和类型和一个**表达式**包含一个或多个元素**操作**的计算结果为单个字符串值的元素。</span><span class="sxs-lookup"><span data-stu-id="14e36-105">To use the `Update` element, you must provide both a column name and type and an **Expression** element containing one or more **Operation** elements that evaluate to a single string value.</span></span>  
  
```  
<ic:Update DataItemName="Name" Type="Type">  
  <ic:Expression>  
    <!-- one or more Operation elements -->  
  </ic:Expression>  
</ic:Update>  
```  
  
### <a name="attributes"></a><span data-ttu-id="14e36-106">特性</span><span class="sxs-lookup"><span data-stu-id="14e36-106">Attributes</span></span>  
  
|<span data-ttu-id="14e36-107">属性名称</span><span class="sxs-lookup"><span data-stu-id="14e36-107">Attribute name</span></span>|<span data-ttu-id="14e36-108">Description</span><span class="sxs-lookup"><span data-stu-id="14e36-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="14e36-109">ColumnName</span><span class="sxs-lookup"><span data-stu-id="14e36-109">ColumnName</span></span>|<span data-ttu-id="14e36-110">BAM 活动检查点的名称。</span><span class="sxs-lookup"><span data-stu-id="14e36-110">BAM activity checkpoint name.</span></span> <span data-ttu-id="14e36-111">这是将更新与提取的数据的检查点。</span><span class="sxs-lookup"><span data-stu-id="14e36-111">This is the checkpoint that will be updated with the extracted data.</span></span>|  
|<span data-ttu-id="14e36-112">类型</span><span class="sxs-lookup"><span data-stu-id="14e36-112">Type</span></span>|<span data-ttu-id="14e36-113">BAM 数据类型的检查点;必须是以下值之一：</span><span class="sxs-lookup"><span data-stu-id="14e36-113">BAM data type of the checkpoint; must be one of the following:</span></span><br /><br /> <span data-ttu-id="14e36-114">-   NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="14e36-114">-   NVARCHAR</span></span><br /><span data-ttu-id="14e36-115">-   DATETIME</span><span class="sxs-lookup"><span data-stu-id="14e36-115">-   DATETIME</span></span><br /><span data-ttu-id="14e36-116">-   INT</span><span class="sxs-lookup"><span data-stu-id="14e36-116">-   INT</span></span><br /><span data-ttu-id="14e36-117">-   FLOAT</span><span class="sxs-lookup"><span data-stu-id="14e36-117">-   FLOAT</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14e36-118">备注</span><span class="sxs-lookup"><span data-stu-id="14e36-118">Remarks</span></span>  
 <span data-ttu-id="14e36-119">中不支持以下操作`Update`表达式：</span><span class="sxs-lookup"><span data-stu-id="14e36-119">The following operations are not supported in the `Update` expression:</span></span>  
  
-   <span data-ttu-id="14e36-120">And</span><span class="sxs-lookup"><span data-stu-id="14e36-120">And</span></span>  
  
-   <span data-ttu-id="14e36-121">等于</span><span class="sxs-lookup"><span data-stu-id="14e36-121">Equals</span></span>  
  
## <a name="example"></a><span data-ttu-id="14e36-122">示例</span><span class="sxs-lookup"><span data-stu-id="14e36-122">Example</span></span>  
 <span data-ttu-id="14e36-123">在以下示例中， **GetContextProperty** WF 操作用于检索**EventTime**属性。</span><span class="sxs-lookup"><span data-stu-id="14e36-123">In the following example, the **GetContextProperty** WF operation is used to retrieve the **EventTime** property.</span></span> <span data-ttu-id="14e36-124">此值将存储为**DATETIME** BAM 活动的"StartOrderProcessing"数据项的类型。</span><span class="sxs-lookup"><span data-stu-id="14e36-124">This value will be stored as a **DATETIME** type for the "StartOrderProcessing" data item for the BAM activity.</span></span>  
  
```  
<ic:Update DataItemName="StartOrderProcessing" Type="DATETIME">  
  <ic:Expression>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>EventTime</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:Update>  
```  
  
## <a name="see-also"></a><span data-ttu-id="14e36-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="14e36-125">See Also</span></span>  
 [<span data-ttu-id="14e36-126">侦听器 OnEvent 元素</span><span class="sxs-lookup"><span data-stu-id="14e36-126">Interceptor OnEvent Element</span></span>](../core/interceptor-onevent-element.md)