---
title: 如何在非英语系统中定义的范围的数值维度警报 |Microsoft Docs
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
ms.openlocfilehash: 703c59f83e0a9af01bcddbea1358a56aa825037b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352480"
---
# <a name="how-to-define-out-of-range-numeric-dimension-alerts-in-non-english-installations"></a><span data-ttu-id="d73ea-102">如何在非英语系统中定义的范围的数值维度警报</span><span class="sxs-lookup"><span data-stu-id="d73ea-102">How to Define Out-of-Range Numeric Dimension Alerts In Non-English Installations</span></span>
<span data-ttu-id="d73ea-103">当设置包含在非英语安装上定义的数值范围维度之外的值的条件的警报，必须手动修改字符串的本地化版本的 BAM 定义**超出范围**.</span><span class="sxs-lookup"><span data-stu-id="d73ea-103">When setting alerts that include a condition for a value that is outside the defined numeric range dimension on non-English installations, you must manually modify the BAM definition with the localized version of the string **out of range**.</span></span>  
  
 <span data-ttu-id="d73ea-104">下表列出了示例的本地化范围外的值。</span><span class="sxs-lookup"><span data-stu-id="d73ea-104">The following table lists examples of localized out-of-range values.</span></span>  
  
|<span data-ttu-id="d73ea-105">语言代码</span><span class="sxs-lookup"><span data-stu-id="d73ea-105">Language code</span></span>|<span data-ttu-id="d73ea-106">已本地化的字符串</span><span class="sxs-lookup"><span data-stu-id="d73ea-106">Localized string</span></span>|  
|-------------------|----------------------|  
|<span data-ttu-id="d73ea-107">CN</span><span class="sxs-lookup"><span data-stu-id="d73ea-107">CN</span></span>|<span data-ttu-id="d73ea-108">超出范围</span><span class="sxs-lookup"><span data-stu-id="d73ea-108">超出范围</span></span>|  
|<span data-ttu-id="d73ea-109">DE</span><span class="sxs-lookup"><span data-stu-id="d73ea-109">DE</span></span>|<span data-ttu-id="d73ea-110">Außerhalb des gültigen Bereichs</span><span class="sxs-lookup"><span data-stu-id="d73ea-110">Außerhalb des gültigen Bereichs</span></span>|  
|<span data-ttu-id="d73ea-111">ES</span><span class="sxs-lookup"><span data-stu-id="d73ea-111">ES</span></span>|<span data-ttu-id="d73ea-112">Fuera de rango</span><span class="sxs-lookup"><span data-stu-id="d73ea-112">Fuera de rango</span></span>|  
|<span data-ttu-id="d73ea-113">FR</span><span class="sxs-lookup"><span data-stu-id="d73ea-113">FR</span></span>|<span data-ttu-id="d73ea-114">hors 会</span><span class="sxs-lookup"><span data-stu-id="d73ea-114">hors limites</span></span>|  
|<span data-ttu-id="d73ea-115">IT</span><span class="sxs-lookup"><span data-stu-id="d73ea-115">IT</span></span>|<span data-ttu-id="d73ea-116">Fuori intervallo</span><span class="sxs-lookup"><span data-stu-id="d73ea-116">Fuori intervallo</span></span>|  
|<span data-ttu-id="d73ea-117">JA</span><span class="sxs-lookup"><span data-stu-id="d73ea-117">JA</span></span>|<span data-ttu-id="d73ea-118">範囲外</span><span class="sxs-lookup"><span data-stu-id="d73ea-118">範囲外</span></span>|  
|<span data-ttu-id="d73ea-119">KO</span><span class="sxs-lookup"><span data-stu-id="d73ea-119">KO</span></span>|<span data-ttu-id="d73ea-120">범위를 벗어남</span><span class="sxs-lookup"><span data-stu-id="d73ea-120">범위를 벗어남</span></span>|  
|<span data-ttu-id="d73ea-121">TW</span><span class="sxs-lookup"><span data-stu-id="d73ea-121">TW</span></span>|<span data-ttu-id="d73ea-122">超過範圍</span><span class="sxs-lookup"><span data-stu-id="d73ea-122">超過範圍</span></span>|  
  
### <a name="to-define-out-of-range-alerts-in-non-english-installations"></a><span data-ttu-id="d73ea-123">若要在非英语系统中定义的范围的警报</span><span class="sxs-lookup"><span data-stu-id="d73ea-123">To define out-of-range alerts in non-English installations</span></span>  
  
1.  <span data-ttu-id="d73ea-124">导航到包含您的 BAM 定义 xml 文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d73ea-124">Navigate to the folder containing your BAM definition xml file.</span></span>  
  
2.  <span data-ttu-id="d73ea-125">使用文本编辑器或 XML 编辑器，打开 BAM 定义文件。</span><span class="sxs-lookup"><span data-stu-id="d73ea-125">Using a text editor or an XML editor, open the BAM definition file.</span></span>  
  
3.  <span data-ttu-id="d73ea-126">查找数值维度的切片器维度。</span><span class="sxs-lookup"><span data-stu-id="d73ea-126">Locate the slicer dimension for the numeric dimension.</span></span> <span data-ttu-id="d73ea-127">例如，如果名为切片器维度**Alerts_NumDim**，则应该查找以下节点：</span><span class="sxs-lookup"><span data-stu-id="d73ea-127">For example, if your slicer dimension is named **Alerts_NumDim**, you would locate the following node:</span></span>  
  
    ```  
    <SlicerDimension Name="Alerts_NumDim">  
    <Level Name="(Out of Range)" />  
    </SlicerDimension>  
    ```  
  
4.  <span data-ttu-id="d73ea-128">更改**超出范围**字符串值与相应的本地化字符串。</span><span class="sxs-lookup"><span data-stu-id="d73ea-128">Change the **Out of Range** string value to the appropriate localized string.</span></span>  
  
5.  <span data-ttu-id="d73ea-129">保存该文件并部署该定义。</span><span class="sxs-lookup"><span data-stu-id="d73ea-129">Save the file and deploy the definition.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d73ea-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="d73ea-130">See Also</span></span>  
 <span data-ttu-id="d73ea-131">[什么是 BAM 定义架构？](../core/what-is-a-bam-definition-schema.md) </span><span class="sxs-lookup"><span data-stu-id="d73ea-131">[What Is a BAM Definition Schema?](../core/what-is-a-bam-definition-schema.md) </span></span>  
 [<span data-ttu-id="d73ea-132">如何部署 BAM 定义</span><span class="sxs-lookup"><span data-stu-id="d73ea-132">How to Deploy BAM Definitions</span></span>](../core/how-to-deploy-bam-definitions.md)