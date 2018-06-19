---
title: 如何在非英语安装中定义的范围外数值维度警报 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f1e0373-eadf-4c6d-9a38-a34d847f310f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea63008680c026eded843e32a7b2c6ff26dc0bf0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238685"
---
# <a name="how-to-define-out-of-range-numeric-dimension-alerts-in-non-english-installations"></a><span data-ttu-id="e3daf-102">如何在非英语系统中定义“超出范围”数值维度警报</span><span class="sxs-lookup"><span data-stu-id="e3daf-102">How to Define Out-of-Range Numeric Dimension Alerts In Non-English Installations</span></span>
<span data-ttu-id="e3daf-103">当设置包括一个值，在非英语安装上定义的数值范围维度之外的条件的警报，你必须手动修改 BAM 定义一同保存本地化版本的字符串**超出范围**.</span><span class="sxs-lookup"><span data-stu-id="e3daf-103">When setting alerts that include a condition for a value that is outside the defined numeric range dimension on non-English installations, you must manually modify the BAM definition with the localized version of the string **out of range**.</span></span>  
  
 <span data-ttu-id="e3daf-104">下表列出了一些本地化后的“超出范围”的值的示例。</span><span class="sxs-lookup"><span data-stu-id="e3daf-104">The following table lists examples of localized out-of-range values.</span></span>  
  
|<span data-ttu-id="e3daf-105">语言代码</span><span class="sxs-lookup"><span data-stu-id="e3daf-105">Language code</span></span>|<span data-ttu-id="e3daf-106">本地化字符串</span><span class="sxs-lookup"><span data-stu-id="e3daf-106">Localized string</span></span>|  
|-------------------|----------------------|  
|<span data-ttu-id="e3daf-107">CN</span><span class="sxs-lookup"><span data-stu-id="e3daf-107">CN</span></span>|<span data-ttu-id="e3daf-108">超出范围</span><span class="sxs-lookup"><span data-stu-id="e3daf-108">超出范围</span></span>|  
|<span data-ttu-id="e3daf-109">DE</span><span class="sxs-lookup"><span data-stu-id="e3daf-109">DE</span></span>|<span data-ttu-id="e3daf-110">Außerhalb des gültigen Bereichs</span><span class="sxs-lookup"><span data-stu-id="e3daf-110">Außerhalb des gültigen Bereichs</span></span>|  
|<span data-ttu-id="e3daf-111">ES</span><span class="sxs-lookup"><span data-stu-id="e3daf-111">ES</span></span>|<span data-ttu-id="e3daf-112">Fuera de rango</span><span class="sxs-lookup"><span data-stu-id="e3daf-112">Fuera de rango</span></span>|  
|<span data-ttu-id="e3daf-113">FR</span><span class="sxs-lookup"><span data-stu-id="e3daf-113">FR</span></span>|<span data-ttu-id="e3daf-114">hors limites</span><span class="sxs-lookup"><span data-stu-id="e3daf-114">hors limites</span></span>|  
|<span data-ttu-id="e3daf-115">IT</span><span class="sxs-lookup"><span data-stu-id="e3daf-115">IT</span></span>|<span data-ttu-id="e3daf-116">Fuori intervallo</span><span class="sxs-lookup"><span data-stu-id="e3daf-116">Fuori intervallo</span></span>|  
|<span data-ttu-id="e3daf-117">JA</span><span class="sxs-lookup"><span data-stu-id="e3daf-117">JA</span></span>|<span data-ttu-id="e3daf-118">範囲外</span><span class="sxs-lookup"><span data-stu-id="e3daf-118">範囲外</span></span>|  
|<span data-ttu-id="e3daf-119">KO</span><span class="sxs-lookup"><span data-stu-id="e3daf-119">KO</span></span>|<span data-ttu-id="e3daf-120">범위를 벗어남</span><span class="sxs-lookup"><span data-stu-id="e3daf-120">범위를 벗어남</span></span>|  
|<span data-ttu-id="e3daf-121">TW</span><span class="sxs-lookup"><span data-stu-id="e3daf-121">TW</span></span>|<span data-ttu-id="e3daf-122">超過範圍</span><span class="sxs-lookup"><span data-stu-id="e3daf-122">超過範圍</span></span>|  
  
### <a name="to-define-out-of-range-alerts-in-non-english-installations"></a><span data-ttu-id="e3daf-123">在非英语系统中定义“超出范围”警报</span><span class="sxs-lookup"><span data-stu-id="e3daf-123">To define out-of-range alerts in non-English installations</span></span>  
  
1.  <span data-ttu-id="e3daf-124">导航到包含 BAM 定义 xml 文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e3daf-124">Navigate to the folder containing your BAM definition xml file.</span></span>  
  
2.  <span data-ttu-id="e3daf-125">使用文本编辑器或 XML 编辑器，打开 BAM 定义文件。</span><span class="sxs-lookup"><span data-stu-id="e3daf-125">Using a text editor or an XML editor, open the BAM definition file.</span></span>  
  
3.  <span data-ttu-id="e3daf-126">查找数值维度的切片维度。</span><span class="sxs-lookup"><span data-stu-id="e3daf-126">Locate the slicer dimension for the numeric dimension.</span></span> <span data-ttu-id="e3daf-127">例如，如果名为切片器维度**Alerts_NumDim**，你将找到以下节点：</span><span class="sxs-lookup"><span data-stu-id="e3daf-127">For example, if your slicer dimension is named **Alerts_NumDim**, you would locate the following node:</span></span>  
  
    ```  
    <SlicerDimension Name="Alerts_NumDim">  
    <Level Name="(Out of Range)" />  
    </SlicerDimension>  
    ```  
  
4.  <span data-ttu-id="e3daf-128">更改**范围**字符串值设为相应的本地化字符串。</span><span class="sxs-lookup"><span data-stu-id="e3daf-128">Change the **Out of Range** string value to the appropriate localized string.</span></span>  
  
5.  <span data-ttu-id="e3daf-129">保存文件，并部署该定义。</span><span class="sxs-lookup"><span data-stu-id="e3daf-129">Save the file and deploy the definition.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3daf-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3daf-130">See Also</span></span>  
 <span data-ttu-id="e3daf-131">[什么是 BAM 定义架构？](../core/what-is-a-bam-definition-schema.md) </span><span class="sxs-lookup"><span data-stu-id="e3daf-131">[What Is a BAM Definition Schema?](../core/what-is-a-bam-definition-schema.md) </span></span>  
 [<span data-ttu-id="e3daf-132">如何部署 BAM 定义</span><span class="sxs-lookup"><span data-stu-id="e3daf-132">How to Deploy BAM Definitions</span></span>](../core/how-to-deploy-bam-definitions.md)