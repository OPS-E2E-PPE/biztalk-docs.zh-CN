---
title: 常规故障排除问题和解答 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2f89d92-0a97-4017-8b8e-6afd8b20eaf4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 373d8cd1c140426427490202d0c8590488a2fcda
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345248"
---
# <a name="general-troubleshooting-questions-and-answers"></a><span data-ttu-id="1c1c5-102">常见疑难问题与解答</span><span class="sxs-lookup"><span data-stu-id="1c1c5-102">General Troubleshooting Questions and Answers</span></span>
<span data-ttu-id="1c1c5-103">本主题有问题和答案，帮助您解决 BizTalk 映射器的问题。</span><span class="sxs-lookup"><span data-stu-id="1c1c5-103">This topic has questions and answers to help you resolve issues with the BizTalk Mapper.</span></span>  
  
## <a name="how-do-i-specify-xslt-output-settings"></a><span data-ttu-id="1c1c5-104">如何指定 XSLT 输出设置？</span><span class="sxs-lookup"><span data-stu-id="1c1c5-104">How do I specify XSLT output settings?</span></span>  
 <span data-ttu-id="1c1c5-105">你可以使用 BizTalk 映射器包括或省略 XML 声明，并控制用于输出实例数据的编码。</span><span class="sxs-lookup"><span data-stu-id="1c1c5-105">You can use the BizTalk Mapper to include or omit XML declarations, and control the encoding used for output instance data.</span></span>  
  
#### <a name="include-or-exclude-an-xml-declaration"></a><span data-ttu-id="1c1c5-106">包含或排除的 XML 声明</span><span class="sxs-lookup"><span data-stu-id="1c1c5-106">Include or exclude an XML declaration</span></span>  
  
1.  <span data-ttu-id="1c1c5-107">在网格视图中，单击映射器网格。</span><span class="sxs-lookup"><span data-stu-id="1c1c5-107">In the Grid view, click the mapper grid.</span></span> <span data-ttu-id="1c1c5-108">**属性**窗口中显示网格属性。</span><span class="sxs-lookup"><span data-stu-id="1c1c5-108">The **Properties** window displays the grid properties.</span></span>  
  
2.  <span data-ttu-id="1c1c5-109">中的下拉列表**忽略 XML 声明**属性中，选择**是**省略 XML 声明，或选择**否**不以省略 XML 声明。</span><span class="sxs-lookup"><span data-stu-id="1c1c5-109">In the drop-down list for the **Omit XML Declaration** property, select **Yes** to omit an XML declaration, or select **No** not to omit an XML declaration.</span></span>  
  
#### <a name="set-encoding-for-output-instance-data"></a><span data-ttu-id="1c1c5-110">设置编码为输出实例数据</span><span class="sxs-lookup"><span data-stu-id="1c1c5-110">Set encoding for output instance data</span></span>  
  
1.  <span data-ttu-id="1c1c5-111">在网格视图中，单击映射器网格。</span><span class="sxs-lookup"><span data-stu-id="1c1c5-111">In the Grid view, click the mapper grid.</span></span> <span data-ttu-id="1c1c5-112">**属性**窗口中显示网格属性。</span><span class="sxs-lookup"><span data-stu-id="1c1c5-112">The **Properties** window displays the grid properties.</span></span>  
  
2.  <span data-ttu-id="1c1c5-113">中的下拉列表**XSLT 编码**属性中，选择的字符集要用于输出实例数据。</span><span class="sxs-lookup"><span data-stu-id="1c1c5-113">In the drop-down list for the **XSLT Encoding** property, select the character set you want to use for the output instance data.</span></span>  
  
## <a name="how-do-i-create-multipart-mappings"></a><span data-ttu-id="1c1c5-114">如何创建多部分映射？</span><span class="sxs-lookup"><span data-stu-id="1c1c5-114">How do I create multipart mappings?</span></span>  
 <span data-ttu-id="1c1c5-115">如果必须一起使用的多个映射，需要将它们合并在业务流程中使用**转换**形状一起进行测试。</span><span class="sxs-lookup"><span data-stu-id="1c1c5-115">If you have multiple maps that are used together, you will need to combine them in an orchestration by using the **Transform** shape to test them together.</span></span> <span data-ttu-id="1c1c5-116">BizTalk 映射器可以测试一次只有一个映射。</span><span class="sxs-lookup"><span data-stu-id="1c1c5-116">The BizTalk Mapper can test only one map at a time.</span></span>  
  
## <a name="why-isnt-my-database-functoid-working"></a><span data-ttu-id="1c1c5-117">为什么我的数据库 functoid 不能正常工作？</span><span class="sxs-lookup"><span data-stu-id="1c1c5-117">Why isn't my database functoid working?</span></span>  
 <span data-ttu-id="1c1c5-118">数据库 functoid**数据库查找**并**值提取程序**不直接返回错误信息; 而是捕获信息并提供到**错误返回** functoid 以供您的映射。</span><span class="sxs-lookup"><span data-stu-id="1c1c5-118">The database functoids **Database Lookup** and **Value Extractor** do not directly return error information; rather, they capture the information and supply it to the **Error Return** functoid for use by your map.</span></span> <span data-ttu-id="1c1c5-119">可以使用**错误返回**functoid 来检测错误如以下方案中所示：</span><span class="sxs-lookup"><span data-stu-id="1c1c5-119">You can use the **Error Return** functoid for error detection as in the following scenarios:</span></span>  
  
- <span data-ttu-id="1c1c5-120">当您的映射具有**数据库查找**或**值提取程序**不按预期方式运行的 functoid。</span><span class="sxs-lookup"><span data-stu-id="1c1c5-120">When your map has a **Database Lookup** or **Value Extractor** functoid that is not behaving as expected.</span></span> <span data-ttu-id="1c1c5-121">若要查看的错误消息，暂时将提取 functoid 映射到输出架构中的字段。</span><span class="sxs-lookup"><span data-stu-id="1c1c5-121">To see the error message, temporarily map the functoid to a field in the output schema.</span></span>  
  
- <span data-ttu-id="1c1c5-122">如果数据库操作失败时，你的应用程序需要不同的消息内容。</span><span class="sxs-lookup"><span data-stu-id="1c1c5-122">If your application expects different message content when database operations fail.</span></span> <span data-ttu-id="1c1c5-123">可以使用**错误返回**functoid 来检测到错误，并将错误消息映射到一个替代结构，以便下游应用程序可以控制的方式作出反应。</span><span class="sxs-lookup"><span data-stu-id="1c1c5-123">You can use the **Error Return** functoid to detect an error and map the error message to an alternate structure so that downstream applications can react in a controlled manner.</span></span>  
  
  <span data-ttu-id="1c1c5-124">若要避免仅在运行时检测到的错误，请确保的第一个参数**错误返回**functoid 是输出**数据库查找**functoid 和不在其他任何 functoid 的输出数据库类别。</span><span class="sxs-lookup"><span data-stu-id="1c1c5-124">To avoid errors that are detected only at run time, make sure that the first parameter to the **Error Return** functoid is the output of a **Database Lookup** functoid and not the output of any other functoid in the Database category.</span></span>  
  
  <span data-ttu-id="1c1c5-125">有关使用详细信息**错误返回**functoid （包括示例），请参阅**Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="1c1c5-125">For more information about using the **Error Return** functoid (including a sample), see the **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="why-is-my-map-failing-when-calling-my-custom-functoid"></a><span data-ttu-id="1c1c5-126">我的地图失败的原因时调用我的自定义 functoid？</span><span class="sxs-lookup"><span data-stu-id="1c1c5-126">Why is my map failing when calling my custom functoid?</span></span>  
 <span data-ttu-id="1c1c5-127">自定义 functoid 必须在安装到全局程序集缓存 (GAC)[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机之前可以通过映射调用它们。</span><span class="sxs-lookup"><span data-stu-id="1c1c5-127">Custom functoids must be installed into the global assembly cache (GAC) on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer before they can be invoked by a map.</span></span> <span data-ttu-id="1c1c5-128">验证已签名并放入 gac 中包含自定义 functoid 的程序集。</span><span class="sxs-lookup"><span data-stu-id="1c1c5-128">Verify that the assembly containing your custom functoid has been signed and placed into the GAC.</span></span> <span data-ttu-id="1c1c5-129">此外，将该程序集复制到文件夹"%BTSINSTALLPATH%\Developer Tools\Mapper Extensions"。</span><span class="sxs-lookup"><span data-stu-id="1c1c5-129">Also, copy the assembly into the folder “%BTSINSTALLPATH%\Developer Tools\Mapper Extensions”.</span></span>  
  
 <span data-ttu-id="1c1c5-130">有关程序集安装到 GAC 的详细信息，请参阅[程序集安装在 GAC 中](../core/assembly-installation-in-the-gac.md)。</span><span class="sxs-lookup"><span data-stu-id="1c1c5-130">For more information about installing assemblies to the GAC, see [Assembly Installation in the GAC](../core/assembly-installation-in-the-gac.md).</span></span> <span data-ttu-id="1c1c5-131">若要查看程序集安装到 GAC 中，导航到的程序集目录你[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]安装目录。</span><span class="sxs-lookup"><span data-stu-id="1c1c5-131">To view assemblies installed in the GAC, navigate to the Assembly directory of your [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] installation directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c1c5-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c1c5-132">See Also</span></span>  
 [<span data-ttu-id="1c1c5-133">排除地图故障</span><span class="sxs-lookup"><span data-stu-id="1c1c5-133">Troubleshooting Maps</span></span>](../core/troubleshooting-maps.md)