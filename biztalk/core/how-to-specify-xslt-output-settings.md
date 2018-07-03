---
title: 如何指定 XSLT 输出设置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4c541432-fd4e-41cc-8bcc-f570ce5df439
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d55a8ddccb996f11315c8856797147083da9123
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998030"
---
# <a name="set-map-compilation-and-output-settings"></a><span data-ttu-id="5d9af-102">设置映射编译和输出设置</span><span class="sxs-lookup"><span data-stu-id="5d9af-102">Set map compilation and output settings</span></span>
<span data-ttu-id="5d9af-103">在 BizTalk 映射器中设置映射属性。</span><span class="sxs-lookup"><span data-stu-id="5d9af-103">Set the map properties in the BizTalk mapper.</span></span> 

<span data-ttu-id="5d9af-104">使用这些映射属性后，可以设置地图的编译方式，包括或排除 XML 声明，以及设置的编码。</span><span class="sxs-lookup"><span data-stu-id="5d9af-104">Using these map properties, you can set how maps are compiled, include or exclude an XML declaration, and set the encoding.</span></span> 

<span data-ttu-id="5d9af-105">本主题演示如何对地图上设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="5d9af-105">This topic shows you how to set these properties on your map.</span></span>

## <a name="set-the-map-level-compilation"></a><span data-ttu-id="5d9af-106">设置地图级别编译</span><span class="sxs-lookup"><span data-stu-id="5d9af-106">Set the map-level compilation</span></span>

<span data-ttu-id="5d9af-107">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** ，选择`XslTransform`或`XslCompiledTransform`类来编译您的映射。</span><span class="sxs-lookup"><span data-stu-id="5d9af-107">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, you choose the `XslTransform` or the `XslCompiledTransform` class to compile your maps.</span></span> 

1. <span data-ttu-id="5d9af-108">在网格视图中打开您的映射。</span><span class="sxs-lookup"><span data-stu-id="5d9af-108">Open your map in the Grid view.</span></span>
2. <span data-ttu-id="5d9af-109">在映射器网格中，右键单击任意位置，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="5d9af-109">Right-click anywhere in the mapper grid, and select **Properties**.</span></span>  
3. <span data-ttu-id="5d9af-110">设置**使用 XSL 转换**属性：</span><span class="sxs-lookup"><span data-stu-id="5d9af-110">Set the **Use XSL Transform** property:</span></span> 

    | <span data-ttu-id="5d9af-111">选项</span><span class="sxs-lookup"><span data-stu-id="5d9af-111">Option</span></span> | <span data-ttu-id="5d9af-112">Description</span><span class="sxs-lookup"><span data-stu-id="5d9af-112">Description</span></span> |
    | --- | --- |
    | <span data-ttu-id="5d9af-113">未定义</span><span class="sxs-lookup"><span data-stu-id="5d9af-113">Undefined</span></span> | <span data-ttu-id="5d9af-114">使用 XslTransform 设置的注册表标志：</span><span class="sxs-lookup"><span data-stu-id="5d9af-114">The registry flag for the XslTransform setting is used:</span></span> <ul><li><span data-ttu-id="5d9af-115">64 位主机实例： `HKLM\SOFTWARE\Microsoft\BizTalk Server\3.0\Configuration`</span><span class="sxs-lookup"><span data-stu-id="5d9af-115">64-bit host instances: `HKLM\SOFTWARE\Microsoft\BizTalk Server\3.0\Configuration`</span></span></li><li><span data-ttu-id="5d9af-116">32 位主机实例和 Visual Studio 的测试映射功能： `HKLM\SOFTWARE\Wow6432Node\Microsoft\BizTalk Server\3.0\Configuration`</span><span class="sxs-lookup"><span data-stu-id="5d9af-116">32-bit host instances, and Visual Studio’s Test Map functionality: `HKLM\SOFTWARE\Wow6432Node\Microsoft\BizTalk Server\3.0\Configuration`</span></span></li></ul> | 
    | <span data-ttu-id="5d9af-117">True</span><span class="sxs-lookup"><span data-stu-id="5d9af-117">True</span></span> | <span data-ttu-id="5d9af-118">映射级别编译属性设置为`XslTransform`（旧版行为）</span><span class="sxs-lookup"><span data-stu-id="5d9af-118">The map level compilation property is set to `XslTransform` (legacy behavior)</span></span> | 
    | <span data-ttu-id="5d9af-119">False</span><span class="sxs-lookup"><span data-stu-id="5d9af-119">False</span></span> | <span data-ttu-id="5d9af-120">映射级别编译属性设置为 `XslCompiledTransform`</span><span class="sxs-lookup"><span data-stu-id="5d9af-120">The map level compilation property is set to `XslCompiledTransform`</span></span> | 

> [!NOTE]
> <span data-ttu-id="5d9af-121">从 BizTalk Server 2013 开始，映射器编译行为已更改从`XslTransform`到`XslCompiledTransform`。</span><span class="sxs-lookup"><span data-stu-id="5d9af-121">Starting with BizTalk Server 2013, the mapper compilation behavior was changed from `XslTransform` to `XslCompiledTransform`.</span></span> <span data-ttu-id="5d9af-122">[什么映射器更新的意义](http://www.quicklearn.com/blog/2013/05/24/what-the-biztalk-server-2013-mapper-updates-mean-for-you/)博客文章提供了很好说明的行为和它的潜在影响。</span><span class="sxs-lookup"><span data-stu-id="5d9af-122">The [What the Mapper Updates Mean for You](http://www.quicklearn.com/blog/2013/05/24/what-the-biztalk-server-2013-mapper-updates-mean-for-you/) blog post provides a great explanation of the behavior, and its potential impact.</span></span> 
> 
> <span data-ttu-id="5d9af-123">从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]，可以选择要编译映射的类。</span><span class="sxs-lookup"><span data-stu-id="5d9af-123">Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], you can choose which class to compile your maps.</span></span> 
  
## <a name="include-or-exclude-an-xml-declaration"></a><span data-ttu-id="5d9af-124">包含或排除的 XML 声明</span><span class="sxs-lookup"><span data-stu-id="5d9af-124">Include or exclude an XML declaration</span></span>  
<span data-ttu-id="5d9af-125">您可以选择指示 XML 声明是否为输出。</span><span class="sxs-lookup"><span data-stu-id="5d9af-125">You can choose whether an XML declaration is output or not.</span></span> 

1. <span data-ttu-id="5d9af-126">在网格视图中打开您的映射。</span><span class="sxs-lookup"><span data-stu-id="5d9af-126">Open your map in the Grid view.</span></span>
2. <span data-ttu-id="5d9af-127">在映射器网格中，右键单击任意位置，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="5d9af-127">Right-click anywhere in the mapper grid, and select **Properties**.</span></span>  
3. <span data-ttu-id="5d9af-128">中的下拉列表**忽略 XML 声明**属性中，选择**是**省略 XML 声明。</span><span class="sxs-lookup"><span data-stu-id="5d9af-128">In the drop-down list for the **Omit XML Declaration** property, select **Yes** to omit an XML declaration.</span></span> <span data-ttu-id="5d9af-129">选择**否**不以省略 XML 声明。</span><span class="sxs-lookup"><span data-stu-id="5d9af-129">Select **No** not to omit an XML declaration.</span></span>  

<span data-ttu-id="5d9af-130">将出现 XML 声明 (如果选择了**否**) 如下所示。</span><span class="sxs-lookup"><span data-stu-id="5d9af-130">An XML declaration would appear (if you selected **No**) similar to the following.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
```  
  
## <a name="set-encoding-for-output-instance-data"></a><span data-ttu-id="5d9af-131">设置编码为输出实例数据</span><span class="sxs-lookup"><span data-stu-id="5d9af-131">Set encoding for output instance data</span></span>  
<span data-ttu-id="5d9af-132">编码为运行时引擎提供确定在创建映射的输出结果时使用的字符集所需的信息。</span><span class="sxs-lookup"><span data-stu-id="5d9af-132">Encoding provides the run-time engine with the information it needs to determine which character set to use when creating the output result of a map.</span></span>  
   
1. <span data-ttu-id="5d9af-133">在网格视图中打开您的映射。</span><span class="sxs-lookup"><span data-stu-id="5d9af-133">Open your map in the Grid view.</span></span>
2. <span data-ttu-id="5d9af-134">在映射器网格中，右键单击任意位置，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="5d9af-134">Right-click anywhere in the mapper grid, and select **Properties**.</span></span>    
3.  <span data-ttu-id="5d9af-135">中的下拉列表**XSLT 编码**属性中，选择的字符集想用于输出实例数据。</span><span class="sxs-lookup"><span data-stu-id="5d9af-135">In the drop-down list for the **XSLT Encoding** property, select the character set you want used for the output instance data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d9af-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d9af-136">See Also</span></span>  
 <span data-ttu-id="5d9af-137">[编译和测试映射](../core/compiling-and-testing-maps.md) </span><span class="sxs-lookup"><span data-stu-id="5d9af-137">[Compiling and Testing Maps](../core/compiling-and-testing-maps.md) </span></span>  
 <span data-ttu-id="5d9af-138">[使用 BizTalk 映射器](../core/using-biztalk-mapper.md) </span><span class="sxs-lookup"><span data-stu-id="5d9af-138">[Using BizTalk Mapper](../core/using-biztalk-mapper.md) </span></span>  
 [<span data-ttu-id="5d9af-139">有效的 BizTalk 映射器 XSLT 编码类型</span><span class="sxs-lookup"><span data-stu-id="5d9af-139">Valid BizTalk Mapper XSLT Encoding Types</span></span>](../core/valid-biztalk-mapper-xslt-encoding-types.md)