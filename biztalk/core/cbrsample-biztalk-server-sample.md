---
title: CBRSample （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, routing
- messages, filters
- outbound maps
- examples, messages
- messages, routing
- examples, outbound maps
- examples, filters
- messages, examples
ms.assetid: 8fba494c-9257-4eed-8b6a-867056147c2c
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b2106998a6ec7af7f2508e199bb1e4e5aa97f73
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983966"
---
# <a name="cbrsample-biztalk-server-sample"></a><span data-ttu-id="7df46-102">CBRSample （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="7df46-102">CBRSample (BizTalk Server Sample)</span></span>
<span data-ttu-id="7df46-103">CBRSample 示例演示如何应用筛选器和出站映射，以便基于内容转换和路由实例消息。</span><span class="sxs-lookup"><span data-stu-id="7df46-103">The CBRSample sample demonstrates how to apply filters and an outbound map to transform and route instance messages based on content.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="7df46-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="7df46-104">What This Sample Does</span></span>  
 <span data-ttu-id="7df46-105">本示例演示如何基于国家/地区代码将包含名称、地址和联系信息的消息路由到两个文件夹之一。</span><span class="sxs-lookup"><span data-stu-id="7df46-105">This sample demonstrates the routing of a message containing name, address, and contact information to one of two folders based on country code.</span></span> <span data-ttu-id="7df46-106">具体而言，本示例执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="7df46-106">Specifically, this sample does the following:</span></span>  

1.  <span data-ttu-id="7df46-107">定义包含人员相关基本信息的示例消息格式，这些基本信息包括带有用户 ID 和全名的标识、带有国家/地区代码的地址以及电话联系信息。</span><span class="sxs-lookup"><span data-stu-id="7df46-107">Defines a sample message format containing basic information about a person including identity with user ID and full name, address with country code, and phone contact information.</span></span>  

2.  <span data-ttu-id="7df46-108">促进**国家/地区代码**这样它可以在端口筛选器控制转换和路由中使用的输入文档中的属性。</span><span class="sxs-lookup"><span data-stu-id="7df46-108">Promotes the **CountryCode** property in the input document so that it can be used in a port filter to control transformation and routing.</span></span>  

3.  <span data-ttu-id="7df46-109">消息转换为加拿大版本时**国家/地区代码**等于 200 或美国版本时**国家/地区代码**等于 100。</span><span class="sxs-lookup"><span data-stu-id="7df46-109">Transforms the message into a Canadian version when **CountryCode** is equal to 200 or a U.S. version when **CountryCode**is equal to 100.</span></span> <span data-ttu-id="7df46-110">这两个转换传递除中间的所有数据初始 (**初始**)。</span><span class="sxs-lookup"><span data-stu-id="7df46-110">Both transforms pass through all data except middle initial (**Initial**).</span></span> <span data-ttu-id="7df46-111">加拿大版本还会将映射**状态**到**省**并**ZipCode**到**PinCode**。</span><span class="sxs-lookup"><span data-stu-id="7df46-111">The Canadian version also maps **State** to **Province** and **ZipCode** to **PinCode**.</span></span>  

4.  <span data-ttu-id="7df46-112">将来自美国的消息路由到 US 目录，将来自加拿大的消息路由到 CAN 目录。</span><span class="sxs-lookup"><span data-stu-id="7df46-112">Routes U.S. messages to the US directory and Canadian messages to the CAN directory.</span></span>  

## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="7df46-113">此示例设计方式和原因</span><span class="sxs-lookup"><span data-stu-id="7df46-113">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="7df46-114">本设计依赖于 BizTalk Server 中的默认发送和接收 XML 管道、属性升级、订阅筛选器和 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 内的出站映射来路由消息。</span><span class="sxs-lookup"><span data-stu-id="7df46-114">The design relies on the default send and receive XML pipelines, property promotion, subscription filters, and outbound maps within [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to route messages.</span></span> <span data-ttu-id="7df46-115">下表显示了设计元素及其选入理由。</span><span class="sxs-lookup"><span data-stu-id="7df46-115">The following table shows design elements and their justification.</span></span>  


|        <span data-ttu-id="7df46-116">设计元素</span><span class="sxs-lookup"><span data-stu-id="7df46-116">Design element</span></span>        |                                                                                                          <span data-ttu-id="7df46-117">选择的原因</span><span class="sxs-lookup"><span data-stu-id="7df46-117">Reason(s) selected</span></span>                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="7df46-118">默认 XML 接收管道</span><span class="sxs-lookup"><span data-stu-id="7df46-118">Default XML receive pipeline</span></span> | <span data-ttu-id="7df46-119">XMLReceive 管道支持属性升级;PassThruReceive 管道却没有。</span><span class="sxs-lookup"><span data-stu-id="7df46-119">-   The XMLReceive pipeline supports property promotion; the PassThruReceive pipeline does not.</span></span><br /><span data-ttu-id="7df46-120">-入站的消息已采用 XML 格式，并且不需要除基本拆装和参与方解析之外的处理。</span><span class="sxs-lookup"><span data-stu-id="7df46-120">-   The inbound message is already in XML format and does not require processing beyond basic disassembly and party resolution.</span></span> |
|      <span data-ttu-id="7df46-121">属性升级</span><span class="sxs-lookup"><span data-stu-id="7df46-121">Property promotion</span></span>      |          <span data-ttu-id="7df46-122">-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]根据属性字段进行路由。</span><span class="sxs-lookup"><span data-stu-id="7df46-122">-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]depends upon property fields to do routing.</span></span> <span data-ttu-id="7df46-123">业务流程使用可分辨字段，并且该字段不能用于路由。</span><span class="sxs-lookup"><span data-stu-id="7df46-123">Distinguished fields are used by orchestrations and cannot be used for routing.</span></span>           |
|     <span data-ttu-id="7df46-124">订阅筛选器</span><span class="sxs-lookup"><span data-stu-id="7df46-124">Subscription filter</span></span>      |                                                <span data-ttu-id="7df46-125">-订阅筛选器执行实际的路由通过捕获符合基于属性的字段的一个或多个条件的消息。</span><span class="sxs-lookup"><span data-stu-id="7df46-125">-   The subscription filter performs the actual routing by capturing messages that meet one or more criteria based on property fields.</span></span>                                                |
|         <span data-ttu-id="7df46-126">出站映射</span><span class="sxs-lookup"><span data-stu-id="7df46-126">Outbound map</span></span>         |                                                     <span data-ttu-id="7df46-127">-映射将数据从一种格式之间转换。</span><span class="sxs-lookup"><span data-stu-id="7df46-127">-   Maps transform data from one format to another.</span></span> <span data-ttu-id="7df46-128">本示例将入站消息映射为美国或加拿大格式。</span><span class="sxs-lookup"><span data-stu-id="7df46-128">The sample maps an inbound message to either a U.S. or Canadian format.</span></span>                                                      |
|         <span data-ttu-id="7df46-129">XMLTransmit</span><span class="sxs-lookup"><span data-stu-id="7df46-129">XMLTransmit</span></span>          |                                                         <span data-ttu-id="7df46-130">-执行基本组装传出 XML 消息;PassThruTransmit 管道未提供其他支持。</span><span class="sxs-lookup"><span data-stu-id="7df46-130">-   Performs basic assembly of outgoing XML messages; the PassThruTransmit pipeline provides no additional support.</span></span>                                                          |

 <span data-ttu-id="7df46-131">可对此基本模式进行扩展，将其用于更加复杂的情形。</span><span class="sxs-lookup"><span data-stu-id="7df46-131">This basic pattern can be extended and used for more complex scenarios.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="7df46-132">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="7df46-132">Where to Find This Sample</span></span>  
 <span data-ttu-id="7df46-133">此示例位于 <`Samples Path>`\Messaging\CBRSample\\。</span><span class="sxs-lookup"><span data-stu-id="7df46-133">This sample is located at <`Samples Path>`\Messaging\CBRSample\\.</span></span>  

 <span data-ttu-id="7df46-134">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="7df46-134">The following table shows the files in this sample and describes their purpose.</span></span>  

|<span data-ttu-id="7df46-135">文件</span><span class="sxs-lookup"><span data-stu-id="7df46-135">File(s)</span></span>|<span data-ttu-id="7df46-136">Description</span><span class="sxs-lookup"><span data-stu-id="7df46-136">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7df46-137">CBRDataCAN.Xml、CBRDataUS.Xml</span><span class="sxs-lookup"><span data-stu-id="7df46-137">CBRDataCAN.Xml, CBRDataUS.Xml</span></span>|<span data-ttu-id="7df46-138">与文件 CBRInputSchema.xsd 中定义的架构相符的示例输入文件。</span><span class="sxs-lookup"><span data-stu-id="7df46-138">Sample input files that conform to the schema defined in the file CBRInputSchema.xsd.</span></span>|  
|<span data-ttu-id="7df46-139">CBRInput2CANMap.btm、CBRInput2USMap.btm</span><span class="sxs-lookup"><span data-stu-id="7df46-139">CBRInput2CANMap.btm, CBRInput2USMap.btm</span></span>|<span data-ttu-id="7df46-140">分别适用于加拿大和美国格式转换的映射文件。</span><span class="sxs-lookup"><span data-stu-id="7df46-140">Map files for the Canadian and U.S. format transformations, respectively.</span></span>|  
|<span data-ttu-id="7df46-141">CBRInputSchema.xsd、CBROutputSchemaCAN.xsd 和 CBROutputSchemaUS.xsd</span><span class="sxs-lookup"><span data-stu-id="7df46-141">CBRInputSchema.xsd, CBROutputSchemaCAN.xsd, CBROutputSchemaUS.xsd</span></span>|<span data-ttu-id="7df46-142">分别适用于输入格式、加拿大输出格式和美国输出格式的架构文件。</span><span class="sxs-lookup"><span data-stu-id="7df46-142">Schema files for the input format, the Canadian output format, and the U.S. output format, respectively.</span></span>|  
|<span data-ttu-id="7df46-143">CBRPromotedPropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="7df46-143">CBRPromotedPropertySchema.xsd</span></span>|<span data-ttu-id="7df46-144">与相对应的升级属性架构文件**国家/地区代码**元素在 XML 输入文件。</span><span class="sxs-lookup"><span data-stu-id="7df46-144">Schema file for the promoted property that corresponds to the **CountryCode** element in the XML input files.</span></span>|  
|<span data-ttu-id="7df46-145">CBRSample.btproj、CBRSample.sln</span><span class="sxs-lookup"><span data-stu-id="7df46-145">CBRSample.btproj, CBRSample.sln</span></span>|<span data-ttu-id="7df46-146">本示例的 BizTalk 项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="7df46-146">BizTalk project and solution files for this sample.</span></span>|  
|<span data-ttu-id="7df46-147">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="7df46-147">Cleanup.bat</span></span>|<span data-ttu-id="7df46-148">用于取消部署程序集并从全局程序集缓存中删除这些程序集。</span><span class="sxs-lookup"><span data-stu-id="7df46-148">Used to undeploy assemblies and remove them from the global assembly cache.</span></span> <span data-ttu-id="7df46-149">删除发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="7df46-149">Removes send and receive ports.</span></span> <span data-ttu-id="7df46-150">根据需要删除 Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="7df46-150">Removes Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="7df46-151">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="7df46-151">Setup.bat</span></span>|<span data-ttu-id="7df46-152">用于生成和初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="7df46-152">Used to build and initialize this sample.</span></span>|  

## <a name="how-to-use-this-sample"></a><span data-ttu-id="7df46-153">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="7df46-153">How to Use This Sample</span></span>  
 <span data-ttu-id="7df46-154">本示例用作基于内容路由消息所需的操作的可运行示例。</span><span class="sxs-lookup"><span data-stu-id="7df46-154">Use this sample as a working example of the actions required to route a message based on content.</span></span>  

## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="7df46-155">生成并初始化本示例</span><span class="sxs-lookup"><span data-stu-id="7df46-155">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="7df46-156">若要生成并初始化 CBRSample 示例，您需要为本示例生成并部署 BizTalk 项目、配置接收端口和位置，并配置两个不同的发送端口。</span><span class="sxs-lookup"><span data-stu-id="7df46-156">To build and initialize the CBRSample sample, you need to build and deploy the BizTalk project for this sample, configure the receive port and location, and configure two different send ports.</span></span>  

#### <a name="to-build-and-deploy-the-biztalk-project-for-this-sample"></a><span data-ttu-id="7df46-157">为本示例生成并部署 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="7df46-157">To build and deploy the BizTalk project for this sample</span></span>  

1. <span data-ttu-id="7df46-158">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="7df46-158">In a command window, navigate to the following folder:</span></span>  

    <span data-ttu-id="7df46-159">`<Samples Path>` **\Messaging\CBRSample**</span><span class="sxs-lookup"><span data-stu-id="7df46-159">`<Samples Path>` **\Messaging\CBRSample**</span></span>  

2. <span data-ttu-id="7df46-160">运行**Setup.bat**，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7df46-160">Run **Setup.bat**, which performs the following actions:</span></span>  

   - <span data-ttu-id="7df46-161">创建输入 (**中**) 和输出文件夹 (**美国**并**可以**) 为本示例。</span><span class="sxs-lookup"><span data-stu-id="7df46-161">Creates the input (**In**) and output folders (**US** and **CAN**) for this sample.</span></span>  

   - <span data-ttu-id="7df46-162">编译并部署本示例的 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 项目。</span><span class="sxs-lookup"><span data-stu-id="7df46-162">Compiles and deploys the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for this sample.</span></span>  

   - <span data-ttu-id="7df46-163">创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置、发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="7df46-163">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="7df46-164">本示例将显示以下警告时创建并绑定端口：</span><span class="sxs-lookup"><span data-stu-id="7df46-164">This sample displays the following warning when creating and binding the ports:</span></span>  
   > 
   >  <span data-ttu-id="7df46-165">**警告： 接收处理程序没有为指定接收位置"CBRReceiveLocation;更新第一个接收处理程序具有匹配传输类型。**</span><span class="sxs-lookup"><span data-stu-id="7df46-165">**Warning: Receive handler not specified for receive location "CBRReceiveLocation"; updating with first receive handler with matching transport type.**</span></span>  
   > 
   >  <span data-ttu-id="7df46-166">可以安全地忽略此警告。</span><span class="sxs-lookup"><span data-stu-id="7df46-166">You can safely ignore this warning.</span></span> <span data-ttu-id="7df46-167">（若要应对可能的命名差异在用户安装中，主机名和接收处理程序中已省略绑定文件。）</span><span class="sxs-lookup"><span data-stu-id="7df46-167">(To accommodate for possible naming differences in user installations, the host name and receive handler have been omitted from the binding file.)</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="7df46-168">在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="7df46-168">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="7df46-169">如果你选择打开并生成本示例中的项目不运行 Setup.bat 的情况下，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。</span><span class="sxs-lookup"><span data-stu-id="7df46-169">If you choose to open and build the project in this sample without running Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="7df46-170">使用此密钥对生成程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="7df46-170">Use this key pair to sign the resulting assembly.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="7df46-171">若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="7df46-171">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="7df46-172">必须运行 Setup.bat 前运行 Cleanup.bat 时间。</span><span class="sxs-lookup"><span data-stu-id="7df46-172">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  

#### <a name="to-prepare-to-configure-the-receive-port-and-location-and-the-send-ports"></a><span data-ttu-id="7df46-173">准备配置接收端口和位置以及发送端口</span><span class="sxs-lookup"><span data-stu-id="7df46-173">To prepare to configure the receive port and location, and the send ports</span></span>  

1.  <span data-ttu-id="7df46-174">在中**Microsoft SQL Management Studio**，选择正确的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="7df46-174">In **Microsoft SQL Management Studio**, select the correct BizTalk Management database.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="7df46-175">BizTalk 管理数据库也称为 BizTalk 配置数据库。</span><span class="sxs-lookup"><span data-stu-id="7df46-175">The BizTalk Management database is also referred to as the BizTalk Configuration database.</span></span>  

#### <a name="to-configure-enlist-and-start-the-us-send-port"></a><span data-ttu-id="7df46-176">配置、登记并启动 U.S. 发送端口</span><span class="sxs-lookup"><span data-stu-id="7df46-176">To configure, enlist, and start the U.S. send port</span></span>  

1.  <span data-ttu-id="7df46-177">在 BizTalk Server 管理控制台中，展开**发送端口**，右键单击**CBRUSSendPort**，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="7df46-177">In the BizTalk Server Administration console, expand **Send Ports**, right-click **CBRUSSendPort**, and then click **Edit**.</span></span>  

2.  <span data-ttu-id="7df46-178">在中**静态单向发送端口属性**对话框中，对话框中，左侧的文件夹树中选择**筛选器和映射&#124;筛选器**，然后通过设置将添加一个新行**属性**到**CBRSample.CountryCode**、 离开**运算符**列设置为**==**，并设置**值**列与**100**。</span><span class="sxs-lookup"><span data-stu-id="7df46-178">In the **Static One-Way Send Port Properties** dialog box, in the folder tree to the left of the dialog box, select **Filters & Mapping &#124; Filters**, and then add a new row by setting **Property** to **CBRSample.CountryCode**, leaving the **Operator** column set to **==**, and setting the **Value** column to **100**.</span></span>  

3.  <span data-ttu-id="7df46-179">在文件夹树中左侧的对话框中，选择**筛选器和映射&#124;出站映射**，将**要应用的映射**属性设置为**CBRSample.CBRInput2USMap**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7df46-179">In the folder tree to the left of the dialog box, select **Filters & Mapping &#124; Outbound Maps**, set the **Map to apply** property to **CBRSample.CBRInput2USMap**, and then click **OK**.</span></span> <span data-ttu-id="7df46-180">您可能需要单击滚动按钮才能显示映射。</span><span class="sxs-lookup"><span data-stu-id="7df46-180">You may have to click the scroll button to bring the map into view.</span></span>  

#### <a name="to-configure-enlist-and-start-the-canadian-send-port"></a><span data-ttu-id="7df46-181">配置、登记并启动 Canadian 发送端口</span><span class="sxs-lookup"><span data-stu-id="7df46-181">To configure, enlist, and start the Canadian send port</span></span>  

1. <span data-ttu-id="7df46-182">在 BizTalk Server 管理控制台中，展开**发送端口**，右键单击**CBRCANSendPort**，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="7df46-182">In the BizTalk Server Administration console, expand **Send Ports**, right-click **CBRCANSendPort**, and then click **Edit**.</span></span>  

2. <span data-ttu-id="7df46-183">在中**静态单向发送端口属性**对话框中，对话框中，左侧的文件夹树中选择**筛选器和映射&#124;筛选器**，然后通过设置将添加一个新行**属性**到**CBRSample.CountryCode**、 离开**运算符**列设置为**==**，并设置**值**列与**200**。</span><span class="sxs-lookup"><span data-stu-id="7df46-183">In the **Static One-Way Send Port Properties** dialog box, in the folder tree to the left of the dialog box, select **Filters & Mapping &#124; Filters**, and then add a new row by setting **Property** to **CBRSample.CountryCode**, leaving the **Operator** column set to **==**, and setting the **Value** column to **200**.</span></span>  

3. <span data-ttu-id="7df46-184">在文件夹树中左侧的对话框中，选择**筛选器和映射&#124;出站映射**，将**要应用的映射**属性设置为**CBRSample.CBRInput2CANMap**然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7df46-184">In the folder tree to the left of the dialog box, select **Filters & Mapping &#124; Outbound Maps**, set the **Map to apply** property to **CBRSample.CBRInput2CANMap**, and then click **OK**.</span></span>  

   <span data-ttu-id="7df46-185">以上步骤可将发送端口连接到接收端口。</span><span class="sxs-lookup"><span data-stu-id="7df46-185">These steps connect the send port to the receive port.</span></span> <span data-ttu-id="7df46-186">此示例使用升级属性，以将这些文档路由。</span><span class="sxs-lookup"><span data-stu-id="7df46-186">The sample uses promoted properties to route the documents.</span></span>  

   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7df46-187"> 现在便可使用本示例。</span><span class="sxs-lookup"><span data-stu-id="7df46-187"> is ready now to work with this sample.</span></span>  

## <a name="running-this-sample"></a><span data-ttu-id="7df46-188">运行本示例</span><span class="sxs-lookup"><span data-stu-id="7df46-188">Running This Sample</span></span>  
 <span data-ttu-id="7df46-189">使用以下过程运行 CBRSample 示例。</span><span class="sxs-lookup"><span data-stu-id="7df46-189">Use the following procedure to run the CBRSample sample.</span></span>  

#### <a name="to-run-this-sample"></a><span data-ttu-id="7df46-190">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="7df46-190">To run this sample</span></span>  

1. <span data-ttu-id="7df46-191">将输入的文件中，复制**CBRDataCAN.xml**并**CBRDataUS.xml**，到以下输入文件夹：</span><span class="sxs-lookup"><span data-stu-id="7df46-191">Copy the input files, **CBRDataCAN.xml** and **CBRDataUS.xml**, into the following input folder:</span></span>  

    <span data-ttu-id="7df46-192">`<Samples Path>` **\Messaging\CBRSample\In**</span><span class="sxs-lookup"><span data-stu-id="7df46-192">`<Samples Path>` **\Messaging\CBRSample\In**</span></span>  

2. <span data-ttu-id="7df46-193">观察如何转换每个文件和两个路由到下列任一输出值的基础的文件夹及其**国家/地区代码**元素 (100 与 200):</span><span class="sxs-lookup"><span data-stu-id="7df46-193">Observe how each of these files is transformed and routed to one of the following two output folders based on the value of their **CountryCode** element (100 versus 200):</span></span>  

   - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7df46-194"> 将转换并将输入的文件的路由**CBRDataCAN.xml**文件夹：</span><span class="sxs-lookup"><span data-stu-id="7df46-194"> transforms and routes the input file **CBRDataCAN.xml** to the folder:</span></span>  

      <span data-ttu-id="7df46-195">`<Samples Path>` **\Messaging\CBRSample\CAN**</span><span class="sxs-lookup"><span data-stu-id="7df46-195">`<Samples Path>` **\Messaging\CBRSample\CAN**</span></span>  

   - <span data-ttu-id="7df46-196">BizTalk Server 将转换并将输入的文件的路由**CBRDataUS.xml**文件夹：</span><span class="sxs-lookup"><span data-stu-id="7df46-196">BizTalk Server transforms and routes the input file **CBRDataUS.xml** to the folder:</span></span>  

      <span data-ttu-id="7df46-197">`<Samples Path>` **\Messaging\CBRSample\US**</span><span class="sxs-lookup"><span data-stu-id="7df46-197">`<Samples Path>` **\Messaging\CBRSample\US**</span></span>  

## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="7df46-198">本示例中使用的类或方法</span><span class="sxs-lookup"><span data-stu-id="7df46-198">Classes or Methods Used in This Sample</span></span>  
 <span data-ttu-id="7df46-199">无。</span><span class="sxs-lookup"><span data-stu-id="7df46-199">None.</span></span>  

## <a name="see-also"></a><span data-ttu-id="7df46-200">请参阅</span><span class="sxs-lookup"><span data-stu-id="7df46-200">See Also</span></span>  
 <span data-ttu-id="7df46-201">[默认管道](../core/default-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="7df46-201">[Default Pipelines](../core/default-pipelines.md) </span></span>  
 <span data-ttu-id="7df46-202">[如何配置发送端口的出站映射](../core/how-to-configure-outbound-maps-for-a-send-port.md) </span><span class="sxs-lookup"><span data-stu-id="7df46-202">[How to Configure Outbound Maps for a Send Port](../core/how-to-configure-outbound-maps-for-a-send-port.md) </span></span>  
 [<span data-ttu-id="7df46-203">消息传送（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="7df46-203">Messaging (BizTalk Server Samples Folder)</span></span>](../core/messaging-biztalk-server-samples-folder.md)