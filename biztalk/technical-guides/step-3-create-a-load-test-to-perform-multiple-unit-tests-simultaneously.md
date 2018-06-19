---
title: 步骤 3： 创建负载测试，以同时执行多个单元测试 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5dd7e31-7188-4edf-9513-ea2725950b47
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76b3d26e9f1dd14463d153c89316b3cf3da0338d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976547"
---
# <a name="step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously"></a><span data-ttu-id="1125c-102">步骤 3： 创建负载测试，以同时执行多个单元测试</span><span class="sxs-lookup"><span data-stu-id="1125c-102">Step 3: Create a Load Test to Perform Multiple Unit Tests Simultaneously</span></span>
<span data-ttu-id="1125c-103">负载测试运行多个实例的一个或多个单元测试，以便可以测量应用程序的性能和能够处理负载。</span><span class="sxs-lookup"><span data-stu-id="1125c-103">Load tests run multiple instances of one or more unit tests so that you can measure your application's performance and ability to handle load.</span></span> <span data-ttu-id="1125c-104">Visual Studio 2010 负载测试的主要组件包括：</span><span class="sxs-lookup"><span data-stu-id="1125c-104">The primary components of a Visual Studio 2010 load test include:</span></span>  
  
-   <span data-ttu-id="1125c-105">**方案**– 一个负载测试中： 你在其中配置测试负载模式、 测试组合模型、 测试组合、 网络组合和 Web 浏览器组合的部分。</span><span class="sxs-lookup"><span data-stu-id="1125c-105">**Scenarios** – The section of a load test where you configure the test load pattern, test mix model, test mix, network mix and Web browser mix.</span></span> <span data-ttu-id="1125c-106">方案容纳模拟复杂的现实世界工作负载配置文件的复杂性。</span><span class="sxs-lookup"><span data-stu-id="1125c-106">Scenarios accommodate the complexity of simulating complex real world work load profiles.</span></span> <span data-ttu-id="1125c-107">有关全面列出的所有负载测试方案属性，请参阅[负载测试方案属性](http://go.microsoft.com/fwlink/?LinkId=208327)(http://go.microsoft.com/fwlink/?LinkId=208327)。</span><span class="sxs-lookup"><span data-stu-id="1125c-107">For a comprehensive listing of all load test scenario properties see [Load Test Scenario Properties](http://go.microsoft.com/fwlink/?LinkId=208327) (http://go.microsoft.com/fwlink/?LinkId=208327).</span></span>  
  
-   <span data-ttu-id="1125c-108">**计数器集**– 一个负载测试中： 你在其中创建特定组或"组"的性能计数器运行负载测试时要收集的部分。</span><span class="sxs-lookup"><span data-stu-id="1125c-108">**Counter Sets** – The section of a load test where you create particular groupings or “Sets” of performance counters to be collected while the load test is running.</span></span> <span data-ttu-id="1125c-109">默认情况下提供多个预定义的计数器集，可以添加自定义计数器集。</span><span class="sxs-lookup"><span data-stu-id="1125c-109">Several predefined counter sets are provided by default and custom counter sets can be added.</span></span> <span data-ttu-id="1125c-110">例如，若要评估网络可以创建自定义计数器的性能设置、 添加相关的网络性能计数器和将其保存到可用的计数器集的列表。</span><span class="sxs-lookup"><span data-stu-id="1125c-110">For example to evaluate Network performance you can create a custom counter set, add the relevant Network performance counters and save it to the list of available counter sets.</span></span> <span data-ttu-id="1125c-111">有关创建和保存的负载测试计数器集的详细信息请参阅[指定在负载测试中的计算机的计数器集](http://go.microsoft.com/fwlink/?LinkId=208328)(http://go.microsoft.com/fwlink/?LinkId=208328)。</span><span class="sxs-lookup"><span data-stu-id="1125c-111">For more information about creating and saving counter sets for load tests see [Specifying the Counter Sets for Computers in a Load Test](http://go.microsoft.com/fwlink/?LinkId=208328) (http://go.microsoft.com/fwlink/?LinkId=208328).</span></span>  
  
-   <span data-ttu-id="1125c-112">**运行设置**– 运行设置中定义的负载测试多个方面，包括测试持续时间，在负载测试中，过程与各种计算机关联的计数器集各种测试验证选项，而测试结果存储选项。</span><span class="sxs-lookup"><span data-stu-id="1125c-112">**Run Settings** – Run settings define multiple aspects of a load test, including the test duration, the counter sets that are associated with various computers during the load test, various test validation options, and test results storage options.</span></span> <span data-ttu-id="1125c-113">你可以创建和存储为每个负载测试中，多个运行的设置，然后选择要在运行测试时使用的特定设置。</span><span class="sxs-lookup"><span data-stu-id="1125c-113">You can create and store multiple run settings for each load test, and then select a particular setting to use when you run the test.</span></span> <span data-ttu-id="1125c-114">使用新建负载测试向导创建负载测试时，将向负载测试添加初始运行设置。</span><span class="sxs-lookup"><span data-stu-id="1125c-114">An initial run setting is added to your load test when you create your load test with the New Load Test Wizard.</span></span> <span data-ttu-id="1125c-115">所有负载测试运行设置属性的完整列表请参阅[负载测试运行设置属性](http://go.microsoft.com/fwlink/?LinkId=208329)(http://go.microsoft.com/fwlink/?LinkId=208329)。</span><span class="sxs-lookup"><span data-stu-id="1125c-115">For a comprehensive listing of all load test run setting properties see [Load Test Run Setting Properties](http://go.microsoft.com/fwlink/?LinkId=208329) (http://go.microsoft.com/fwlink/?LinkId=208329).</span></span>  
  
 <span data-ttu-id="1125c-116">负载测试是使用新建负载测试向导中，编辑使用负载测试编辑器中，并分析负载测试分析器中创建的。</span><span class="sxs-lookup"><span data-stu-id="1125c-116">Load tests are created using the New Load Test Wizard, edited with the Load Test Editor, and analyzed in the Load Test Analyzer.</span></span> <span data-ttu-id="1125c-117">在 Microsoft Visual Studio Ultimate 版本中包括所有这些工具。</span><span class="sxs-lookup"><span data-stu-id="1125c-117">All these tools are included in Microsoft Visual Studio Ultimate edition.</span></span> <span data-ttu-id="1125c-118">有关创建和编辑负载测试在 Visual Studio 2010 旗舰版中的详细信息请参阅[创建和编辑负载测试](http://go.microsoft.com/fwlink/?LinkId=208308)(http://go.microsoft.com/fwlink/?LinkId=208308)。</span><span class="sxs-lookup"><span data-stu-id="1125c-118">For more information about creating and editing load tests in Visual Studio 2010 Ultimate edition see [Creating and Editing Load Tests](http://go.microsoft.com/fwlink/?LinkId=208308) (http://go.microsoft.com/fwlink/?LinkId=208308).</span></span>  
  
 <span data-ttu-id="1125c-119">向测试项目中所述的步骤在以下部分，以添加负载测试的按照[步骤 1： 创建单元测试将文档提交给 BizTalk Server](../technical-guides/step-1-create-a-unit-test-to-submit-documents-to-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="1125c-119">Follow the steps in the sections below to add a load test to the test project described in [Step 1: Create a Unit Test to Submit Documents to BizTalk Server](../technical-guides/step-1-create-a-unit-test-to-submit-documents-to-biztalk-server.md).</span></span> <span data-ttu-id="1125c-120">这些步骤还描述如何配置**方案**，**计数器集**，和**运行设置**为负载测试。</span><span class="sxs-lookup"><span data-stu-id="1125c-120">These steps also describe how to configure the **Scenarios**, **Counter Sets**, and **Run Settings** for a load test.</span></span>  
  
##  <a name="BKMK_StepLoadTest"></a><span data-ttu-id="1125c-121">添加一个负载测试和配置在负载测试方案、 计数器集，和运行设置</span><span class="sxs-lookup"><span data-stu-id="1125c-121">Add a Load Test and Configure the Load Test Scenario, Counter Sets, and Run Settings</span></span>  
 <span data-ttu-id="1125c-122">本主题介绍如何使用**新建负载测试向导**添加负载测试的测试项目以及如何配置负载测试以满足特定需求。</span><span class="sxs-lookup"><span data-stu-id="1125c-122">This topic describes how to use the **New Load Test Wizard** to add a load test to a test project and how to configure the load test to meet specific needs.</span></span>  
  
### <a name="use-the-new-load-test-wizard-to-add-a-load-test-to-the-test-project"></a><span data-ttu-id="1125c-123">使用新建负载测试向导将负载测试添加到测试项目</span><span class="sxs-lookup"><span data-stu-id="1125c-123">Use the New Load Test Wizard to Add a Load Test to the Test Project</span></span>  
 <span data-ttu-id="1125c-124">请按照下列步骤以将负载测试添加到测试项目使用新建负载测试向导。</span><span class="sxs-lookup"><span data-stu-id="1125c-124">Follow these steps to add a load test to a test project using the New Load Test Wizard.</span></span>  
  
1.  <span data-ttu-id="1125c-125">打开**负载测试**如果尚未打开的 Visual Studio 2010 中的解决方案。</span><span class="sxs-lookup"><span data-stu-id="1125c-125">Open the **Load Test** solution in Visual Studio 2010 if it is not already open.</span></span>  
  
2.  <span data-ttu-id="1125c-126">将文件夹添加到 BTSLoad 项目中;此文件夹将包含任何为此项目的一部分创建的负载测试。</span><span class="sxs-lookup"><span data-stu-id="1125c-126">Add a folder to the BTSLoad project; this folder will contain any load tests that are created as part of this project.</span></span> <span data-ttu-id="1125c-127">在解决方案资源管理器，右键单击 BTSLoad 项目，指向**添加**，然后单击**新文件夹**。</span><span class="sxs-lookup"><span data-stu-id="1125c-127">In Solution Explorer, right-click the BTSLoad project, point to **Add**, and click **New Folder**.</span></span> <span data-ttu-id="1125c-128">一个带有突出显示的文本的文件夹图标**NewFolder1**将出现在 BTSLoad 项目，类型**LoadTests**更改突出显示的文本，按 Enter 键以完成创建的文件夹 C:\Projects\LoadTest\BTSLoad\LoadTests。</span><span class="sxs-lookup"><span data-stu-id="1125c-128">A folder icon with the highlighted text **NewFolder1** will appear under the BTSLoad project, type **LoadTests** to change the highlighted text and press the Enter key to complete creation of the folder C:\Projects\LoadTest\BTSLoad\LoadTests.</span></span>  
  
3.  <span data-ttu-id="1125c-129">在解决方案资源管理器，右键单击**BTSLoad**项目，指向**添加**，然后单击**负载测试**启动**新建负载测试向导**.</span><span class="sxs-lookup"><span data-stu-id="1125c-129">In Solution Explorer, right-click on the **BTSLoad** project, point to **Add**, and then click **Load Test** to start the **New Load Test Wizard**.</span></span>  
  
4.  <span data-ttu-id="1125c-130">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="1125c-130">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="1125c-131">上**编辑负载测试方案设置**下页上**输入负载测试方案的名称：** 类型**BTS_Messaging_Step**。</span><span class="sxs-lookup"><span data-stu-id="1125c-131">On the **Edit Settings for a Load Test Scenario** page under **Enter a name for the load test scenario:** type **BTS_Messaging_Step**.</span></span> <span data-ttu-id="1125c-132">下**思考时间配置文件**选择**不使用思考时间**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1125c-132">Under **Think time profile** select **Do not use think times** and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="1125c-133">上**编辑负载模式设置的负载测试方案**页上，选择**分级负载**，输入下面的值，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1125c-133">On the **Edit load pattern settings for a load test scenario** page select **Step load**, enter the values below and then click **Next**.</span></span>  
  
    -   <span data-ttu-id="1125c-134">**开始用户计数：** 30 用户</span><span class="sxs-lookup"><span data-stu-id="1125c-134">**Start user count:** 30 users</span></span>  
  
    -   <span data-ttu-id="1125c-135">**单步持续时间：** 60 秒</span><span class="sxs-lookup"><span data-stu-id="1125c-135">**Step duration:** 60 seconds</span></span>  
  
    -   <span data-ttu-id="1125c-136">**单步用户计数：** 10 个用户</span><span class="sxs-lookup"><span data-stu-id="1125c-136">**Step user count:** 10 users</span></span>  
  
    -   <span data-ttu-id="1125c-137">**最大用户数**80 用户</span><span class="sxs-lookup"><span data-stu-id="1125c-137">**Maximum user count** 80 users</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1125c-138">应用设置为分级负载模式时应计算所需的所有步骤为增量来完成的时间量。</span><span class="sxs-lookup"><span data-stu-id="1125c-138">When applying settings for a step load pattern you should calculate the amount of time required for all step increments to complete.</span></span> <span data-ttu-id="1125c-139">例如，使用负载测试使用上面指定的负载模式设置将需要 5 分钟才能完成所有 60 秒的增量当逐从 30 掌握到 80 用户。</span><span class="sxs-lookup"><span data-stu-id="1125c-139">For example, using the load pattern settings specified above the load test will need 5 minutes to complete all of the 60 second step increments when ramping up from 30 to 80 users.</span></span> <span data-ttu-id="1125c-140">在新建负载测试向导将显示有关指定负载测试的长度的选项的最后一页，其中将**负载测试持续时间**。</span><span class="sxs-lookup"><span data-stu-id="1125c-140">On the last page of the New Load Test Wizard you will be presented with options for specifying the length of the load test, one of which will be **Load Test Duration**.</span></span> <span data-ttu-id="1125c-141">如果你已具有为计算所需的所有步骤才能完成，那么很简单的任务输入值 （在此情况下为 5 分钟） 的增量的时间**负载测试持续时间**。</span><span class="sxs-lookup"><span data-stu-id="1125c-141">If you have already calculated the time required for all step increments to complete then it is a straightforward task to enter the value (5 minutes in this case) for **Load Test Duration**.</span></span>  
  
7.  <span data-ttu-id="1125c-142">上**选择负载测试测试组合模型**页上，选择**基于虚拟用户数**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1125c-142">On the **Select a test mix model for the load test** page select **Based on the number of virtual users** and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="1125c-143">上**向负载测试方案添加测试并编辑测试组合**页上，单击**添加**按钮。</span><span class="sxs-lookup"><span data-stu-id="1125c-143">On the **Add tests to the load test scenario and edit the test mix** page click the **Add** button.</span></span>  
  
9. <span data-ttu-id="1125c-144">下**可用测试**双击**BTSMessaging**和**BTSMessaging2**将这些单元测试添加到的列表**选定的测试**。</span><span class="sxs-lookup"><span data-stu-id="1125c-144">Under **Available tests** double-click **BTSMessaging** and **BTSMessaging2** to add these unit tests to the list of **Selected tests**.</span></span> <span data-ttu-id="1125c-145">单击**确定**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1125c-145">Click **OK** and then click **Next**.</span></span>  
  
10. <span data-ttu-id="1125c-146">上**将网络类型添加到负载测试方案并编辑网络组合**页验证**网络类型**设置为**LAN**与**分发**的**100%** ，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1125c-146">On the **Add network types to a load test scenario and edit the network mix** page verify that **Network Type** is set to **LAN** with a **Distribution** of **100%** and then click **Next**.</span></span>  
  
11. <span data-ttu-id="1125c-147">上**指定要在负载测试运行期间使用计数器集监视的计算机**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1125c-147">On the **Specify computers to monitor with counter sets during load test run** page click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1125c-148">不将计算机添加到负载测试在此时间。</span><span class="sxs-lookup"><span data-stu-id="1125c-148">Do not add computers to the load test at this time.</span></span> <span data-ttu-id="1125c-149">新建负载测试向导将仅允许你将计算机相关联的预定义的计数器集，并且此负载测试需要预定义如何使用和*自定义*计数器集中。</span><span class="sxs-lookup"><span data-stu-id="1125c-149">The New Load Test Wizard will only allow you to associate computers with predefined counter sets, and this load test requires the use of both predefined and *custom* counter sets.</span></span> <span data-ttu-id="1125c-150">完成向导并保存负载测试之后可以编辑负载测试添加自定义计数器集和配置要监视使用预定义的计算机的负载测试*和*自定义计数器集。</span><span class="sxs-lookup"><span data-stu-id="1125c-150">After the wizard is complete and the load test is saved you can edit the load test to add custom counter sets and configure the load test to monitor computers using both predefined *and* custom counter sets.</span></span>  
  
     <span data-ttu-id="1125c-151">上**查看和编辑运行负载测试设置**页上，输入以下值：</span><span class="sxs-lookup"><span data-stu-id="1125c-151">On the **Review and edit run settings for a load test** page enter the following values:</span></span>  
  
    1.  <span data-ttu-id="1125c-152">选择**负载测试持续时间**。</span><span class="sxs-lookup"><span data-stu-id="1125c-152">Select **Load test duration**.</span></span>  
  
    2.  <span data-ttu-id="1125c-153">**预热持续时间 (hh mm ss)** 30 秒</span><span class="sxs-lookup"><span data-stu-id="1125c-153">**Warm-up duration (hh mm ss)** 30 seconds</span></span>  
  
    3.  <span data-ttu-id="1125c-154">**运行持续时间 (hh mm ss)** 5 分钟</span><span class="sxs-lookup"><span data-stu-id="1125c-154">**Run duration (hh mm ss)** 5 minutes</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="1125c-155">为分配的时间**运行持续时间**应等于所需的所有步骤才能完成步骤 5 更高版本或 5 分钟，对于此示例中所述的增量的时间量。</span><span class="sxs-lookup"><span data-stu-id="1125c-155">The time allocated for **Run duration** should equal the amount of time required for all step increments to complete as described in step 5 above, or 5 minutes for this example.</span></span>  
  
    4.  <span data-ttu-id="1125c-156">**采样率**5 秒</span><span class="sxs-lookup"><span data-stu-id="1125c-156">**Sampling rate** 5 seconds</span></span>  
  
    5.  <span data-ttu-id="1125c-157">**说明**（可选） 输入负载测试此处的说明。</span><span class="sxs-lookup"><span data-stu-id="1125c-157">**Description** (optional), Enter a description for the load test here.</span></span>  
  
    6.  <span data-ttu-id="1125c-158">**测试失败时保存日志**True</span><span class="sxs-lookup"><span data-stu-id="1125c-158">**Save Log on Test Failure** True</span></span>  
  
    7.  <span data-ttu-id="1125c-159">**验证级别**低 – 调用标记为低的验证规则</span><span class="sxs-lookup"><span data-stu-id="1125c-159">**Validation level** Low – invoke validation rules marked low</span></span>  
  
12. <span data-ttu-id="1125c-160">单击**完成**以关闭新建负载测试向导。</span><span class="sxs-lookup"><span data-stu-id="1125c-160">Click **Finish** to close the New Load Test Wizard.</span></span>  
  
13. <span data-ttu-id="1125c-161">单击**文件**菜单，然后选择**保存\<负载测试名称\>作为.loadtest**。</span><span class="sxs-lookup"><span data-stu-id="1125c-161">Click the **File** menu and select **Save \<Load Test Name\>.loadtest As**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1125c-162">在此示例中，<Load Test Name>将是由 Visual Studio 2010 中，通常 loadtestx.loadtest，分配给负载测试文件的名称，除非已手动更改该文件的名称。</span><span class="sxs-lookup"><span data-stu-id="1125c-162">In this example, <Load Test Name> will be the name assigned to the load test file by Visual Studio 2010, typically loadtestx.loadtest, unless the name of the file has already been manually changed.</span></span>  
  
14. <span data-ttu-id="1125c-163">将文件保存到先前创建的 C:\Projects\LoadTest\BTSLoad\LoadTests 目录。</span><span class="sxs-lookup"><span data-stu-id="1125c-163">Save the file to the C:\Projects\LoadTest\BTSLoad\LoadTests directory created earlier.</span></span> <span data-ttu-id="1125c-164">它可能会有用的情形; 使用的名称保存该文件在此示例中的方案的名称是 BTS_Messaging_Step，因此 loadtest 文件将另存为 C:\Projects\LoadTest\BTSLoad\LoadTests\BTS_Messaging_Step.loadtest。</span><span class="sxs-lookup"><span data-stu-id="1125c-164">It may be useful to save the file with the name used for the scenario; in this example the scenario name is BTS_Messaging_Step so the loadtest file would be saved as C:\Projects\LoadTest\BTSLoad\LoadTests\BTS_Messaging_Step.loadtest.</span></span>  
  
###  <a name="BKMK_BTSCounters"></a><span data-ttu-id="1125c-165">添加自定义计数器集来测量 BizTalk Server 关键绩效指标 (KPI)</span><span class="sxs-lookup"><span data-stu-id="1125c-165">Add a Custom Counter Set to Measure BizTalk Server Key Performance Indicators (KPI)</span></span>  
 <span data-ttu-id="1125c-166">请按照下列步骤以添加计数器集与度量值用于确定最大可持续吞吐量 (MST) 的 BizTalk Server 应用程序所需的 BizTalk Server KPI 的性能计数器：</span><span class="sxs-lookup"><span data-stu-id="1125c-166">Follow these steps to add a counter set with performance counters that measure BizTalk Server KPI required for determining Maximum Sustainable Throughput (MST) of the BizTalk Server application:</span></span>  
  
1.  <span data-ttu-id="1125c-167">在解决方案资源管理器双击在负载测试在上一节，以在负载测试编辑器中查看负载测试中创建。</span><span class="sxs-lookup"><span data-stu-id="1125c-167">In Solution Explorer double-click the load test that you created in the previous section to view the load test in Load Test editor.</span></span>  
  
2.  <span data-ttu-id="1125c-168">在负载测试编辑器中，单击以展开**计数器集**。</span><span class="sxs-lookup"><span data-stu-id="1125c-168">In Load Test editor, click to expand **Counter Sets**.</span></span> <span data-ttu-id="1125c-169">请注意，BizTalk Server 没有预定义的计数器集，因此必须将"BizTalk Server"计数器集添加到计数器的列表的自定义设置。</span><span class="sxs-lookup"><span data-stu-id="1125c-169">Notice that there is no predefined counter set for BizTalk Server, therefore a custom “BizTalk Server” counter set must be added to the list of counter sets.</span></span>  
  
3.  <span data-ttu-id="1125c-170">右键单击**计数器集**和选择**添加自定义计数器集**。</span><span class="sxs-lookup"><span data-stu-id="1125c-170">Right-click **Counter Sets** and select **Add Custom Counter Set**.</span></span> <span data-ttu-id="1125c-171">默认情况下，此操作将创建自定义计数器集同名**Custom1**。</span><span class="sxs-lookup"><span data-stu-id="1125c-171">By default this action will create a custom counter set with the name **Custom1**.</span></span>  
  
4.  <span data-ttu-id="1125c-172">右键单击**Custom1**计数器集和选择**属性**焦点设置到**属性**Custom1 计数器集的对话框。</span><span class="sxs-lookup"><span data-stu-id="1125c-172">Right-click the **Custom1** counter set and select **Properties** to set focus to the **Properties** dialog for the Custom1 counter set.</span></span>  
  
5.  <span data-ttu-id="1125c-173">双击名称**Custom1**中**属性**对话框中，键入**BizTalk** ，然后按 ENTER 键，若要重命名自定义计数器集**BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="1125c-173">Double-click the name **Custom1** in the **Properties** dialog, type **BizTalk** and then press the ENTER key to rename the custom counter set to **BizTalk**.</span></span>  
  
6.  <span data-ttu-id="1125c-174">在负载测试编辑器中，右键单击**BizTalk**计数器集和选择**添加计数器**。</span><span class="sxs-lookup"><span data-stu-id="1125c-174">In Load Test Editor, right-click the **BizTalk** counter set and select **Add Counters**.</span></span>  
  
7.  <span data-ttu-id="1125c-175">下**计算机**，BizTalk Server 组，以显示包括 BizTalk Server 性能计数器的性能监视器类别中键入一个 BizTalk Server 计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="1125c-175">Under **Computer**, type the name of one of the BizTalk Server computers in the BizTalk Server group to display performance monitor categories that include BizTalk Server performance counters.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="1125c-176">若要确保列出了所有的 BizTalk Server 性能类别和性能计数器，可能需要键入完全限定的域名 （或 IP 地址） 中的组中的 BizTalk 服务器并且你可能还需要在上启动的以下主机实例BizTalk Server 计算机。</span><span class="sxs-lookup"><span data-stu-id="1125c-176">To ensure that all BizTalk Server performance categories and performance counters are listed, you may need to type in the fully qualified domain name (or IP Address) of a BizTalk Server in the group and you may also need to start the instances of the following hosts on the BizTalk Server computer.</span></span>  
    >   
    >  -   <span data-ttu-id="1125c-177">绑定到将在负载测试期间运行的业务流程的 BizTalk 主机实例。</span><span class="sxs-lookup"><span data-stu-id="1125c-177">Instances of BizTalk hosts which are bound to orchestrations that will run during the load test.</span></span>  
    > -   <span data-ttu-id="1125c-178">BizTalk 主机配置为发送或接收处理程序将在负载测试期间运行的适配器的实例。</span><span class="sxs-lookup"><span data-stu-id="1125c-178">Instances of BizTalk hosts configured as send or receive handlers for adapters that will run during the load test.</span></span>  
  
8.  <span data-ttu-id="1125c-179">BizTalk Server 提供很了一组广泛的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="1125c-179">BizTalk Server provides quite an extensive set of performance counters.</span></span> <span data-ttu-id="1125c-180">为了确定 BizTalk server 最大可持续性能 (MST) 应用程序只需将添加以下 BizTalk Server 性能计数器来**BizTalk**自定义计数器集：</span><span class="sxs-lookup"><span data-stu-id="1125c-180">For purposes of determining the Maximum Sustainable Performance (MST) of a BizTalk Server application you only need to add the following BizTalk Server performance counters to the **BizTalk** custom counter set:</span></span>  
  
    |<span data-ttu-id="1125c-181">性能类别</span><span class="sxs-lookup"><span data-stu-id="1125c-181">Performance Category</span></span>|<span data-ttu-id="1125c-182">性能计数器</span><span class="sxs-lookup"><span data-stu-id="1125c-182">Performance Counter</span></span>|  
    |--------------------------|-------------------------|  
    |<span data-ttu-id="1125c-183">处理器</span><span class="sxs-lookup"><span data-stu-id="1125c-183">Processor</span></span>|<span data-ttu-id="1125c-184">%Processor Time 的 _Total 计数器实例。</span><span class="sxs-lookup"><span data-stu-id="1125c-184">% Processor Time for the _Total counter instance.</span></span>|  
    |<span data-ttu-id="1125c-185">BizTalk:Message 框： 常规计数器</span><span class="sxs-lookup"><span data-stu-id="1125c-185">BizTalk:Message Box: General Counters</span></span>|<span data-ttu-id="1125c-186">假脱机的大小 *\<BizTalk MessageBox 数据库名称\>*:*\<SQL Server 实例名称\>* 计数器实例。</span><span class="sxs-lookup"><span data-stu-id="1125c-186">Spool Size for the *\<BizTalk MessageBox database name\>*:*\<SQL Server instance name\>* counter instance.</span></span> <span data-ttu-id="1125c-187">**注意：***\<BizTalk MessageBox 数据库名称\>* 和 *\<SQL Server 实例名称\>* 的只是占位符BizTalk MessageBox 数据库和保存 BizTalk MessageBox 数据库的 SQL Server 实例的实际名称。  </span><span class="sxs-lookup"><span data-stu-id="1125c-187">**Note:**  *\<BizTalk MessageBox database name\>* and *\<SQL Server instance name\>* are just placeholders for the actual names of the BizTalk MessageBox database and the SQL Server instance that houses the BizTalk MessageBox database.</span></span> <span data-ttu-id="1125c-188">这些占位符应替换的 BizTalk MessageBox 数据库和关联的 SQL Server 实例的实际名称。</span><span class="sxs-lookup"><span data-stu-id="1125c-188">These placeholders should be replaced with the actual names of the BizTalk MessageBox database and associated SQL Server instance.</span></span>|  
    |<span data-ttu-id="1125c-189">BizTalk:Messaging</span><span class="sxs-lookup"><span data-stu-id="1125c-189">BizTalk:Messaging</span></span>|<span data-ttu-id="1125c-190">文档接收每秒接收主机计数器实例。</span><span class="sxs-lookup"><span data-stu-id="1125c-190">Documents received/Sec for the receive host counter instance.</span></span><br /><br /> <span data-ttu-id="1125c-191">文档处理每秒传输主机计数器实例。</span><span class="sxs-lookup"><span data-stu-id="1125c-191">Documents processed/Sec for the transmit host counter instance.</span></span>|  
    |<span data-ttu-id="1125c-192">BizTalk：消息代理</span><span class="sxs-lookup"><span data-stu-id="1125c-192">BizTalk:Message Agent</span></span>|<span data-ttu-id="1125c-193">文档的消息传送传入速率接收主机。</span><span class="sxs-lookup"><span data-stu-id="1125c-193">Message delivery incoming rate for the document receive host.</span></span>|  
    |<span data-ttu-id="1125c-194">BizTalk：消息代理</span><span class="sxs-lookup"><span data-stu-id="1125c-194">BizTalk:Message Agent</span></span>|<span data-ttu-id="1125c-195">为文档传输主机发布传出速率的消息。</span><span class="sxs-lookup"><span data-stu-id="1125c-195">Message publishing outgoing rate for the document transmit host.</span></span>|  
    |<span data-ttu-id="1125c-196">XLANG/s 业务流程</span><span class="sxs-lookup"><span data-stu-id="1125c-196">XLANG/s Orchestrations</span></span>|<span data-ttu-id="1125c-197">业务流程完成每秒处理业务流程主机。</span><span class="sxs-lookup"><span data-stu-id="1125c-197">Orchestrations completed/sec for the Orchestration processing host.</span></span>|  
  
### <a name="modify-run-settings-to-map-counter-sets-to-appropriate-computers"></a><span data-ttu-id="1125c-198">修改运行的设置，以将计数器集映射到合适的计算机</span><span class="sxs-lookup"><span data-stu-id="1125c-198">Modify Run Settings to Map Counter Sets to Appropriate Computers</span></span>  
 <span data-ttu-id="1125c-199">请按照下列步骤以将与负载测试的合适的计算机的相应的计数器集映射：</span><span class="sxs-lookup"><span data-stu-id="1125c-199">Follow these steps to map the appropriate counter sets with the appropriate computers for the load test:</span></span>  
  
1.  <span data-ttu-id="1125c-200">在**负载测试编辑器**，右键单击**运行设置**和选择**管理计数器集**。</span><span class="sxs-lookup"><span data-stu-id="1125c-200">In **Load Test Editor**, right-click **Run Settings** and select **Manage Counter Sets**.</span></span>  
  
2.  <span data-ttu-id="1125c-201">单击**将计算机添加**将新计算机添加到列表。</span><span class="sxs-lookup"><span data-stu-id="1125c-201">Click **Add Computer** to add a new computer to the list.</span></span> <span data-ttu-id="1125c-202">带突出显示的文本的图标**新计算机**将出现在**要监视的计算机和计数器集**。</span><span class="sxs-lookup"><span data-stu-id="1125c-202">An icon with the highlighted text **New Computer** will appear under **Computers and counter sets to monitor**.</span></span> <span data-ttu-id="1125c-203">通过键入你想要添加到列表中的计算机的名称将突出显示的文本。</span><span class="sxs-lookup"><span data-stu-id="1125c-203">Replace the highlighted text by typing the name of the computer you would like to add to the list.</span></span>  
  
3.  <span data-ttu-id="1125c-204">后将计算机添加到列表中，单击此项可展开的可用计数器集列表，然后单击以选择一个或多个可用的计数器集以将计数器集与计算机关联。</span><span class="sxs-lookup"><span data-stu-id="1125c-204">After adding the computer to the list, click to expand the list of available counter sets and then click to select one or more of the available counter sets to associate the counter set(s) with the computer.</span></span>  
  
4.  <span data-ttu-id="1125c-205">重复步骤 2 和 3，直到你具有与要收集性能数据的所有计算机的计数器集。</span><span class="sxs-lookup"><span data-stu-id="1125c-205">Repeat steps 2 and 3 until you have associated counter sets with all computers for which you would like to collect performance data.</span></span>  
  
###  <a name="BKMK_TestSettings"></a><span data-ttu-id="1125c-206">将测试设置文件添加到解决方案以运行测试并远程收集数据</span><span class="sxs-lookup"><span data-stu-id="1125c-206">Add a Test Settings File to the Solution to Run Tests and Collect Data Remotely</span></span>  
 <span data-ttu-id="1125c-207">若要配置负载测试，以使用你在中创建的测试控制器和测试代理计算机[步骤 2： 配置负载测试控制器和代理计算机](../technical-guides/step-2-configure-load-test-controller-and-agent-computers.md)，按照中的步骤[添加为远程执行的测试设置或数据收集到你的解决方案](http://go.microsoft.com/fwlink/?LinkId=209182)(http://go.microsoft.com/fwlink/?LinkId=209182) 如下所述：</span><span class="sxs-lookup"><span data-stu-id="1125c-207">To configure the Load test to use the Test Controller and Test Agent computers that you created in [Step 2: Configure Load Test Controller and Agent Computers](../technical-guides/step-2-configure-load-test-controller-and-agent-computers.md), follow the steps in [Add a test settings for remote execution or data collection to your solution](http://go.microsoft.com/fwlink/?LinkId=209182)(http://go.microsoft.com/fwlink/?LinkId=209182) as noted below:</span></span>  
  
1.  <span data-ttu-id="1125c-208">对于步骤 3 中，输入名称**BizTalkLoadTest**</span><span class="sxs-lookup"><span data-stu-id="1125c-208">For Step 3, enter the name **BizTalkLoadTest**</span></span>  
  
2.  <span data-ttu-id="1125c-209">忽略步骤 6，因为已经在步骤 3 中输入一个名称。</span><span class="sxs-lookup"><span data-stu-id="1125c-209">Ignore Step 6 because you have already entered a name in Step 3.</span></span>  
  
3.  <span data-ttu-id="1125c-210">对于步骤 7 中，输入"These are 一个远程测试运行的默认测试设置"下**说明**。</span><span class="sxs-lookup"><span data-stu-id="1125c-210">For Step 7, enter “These are default test settings for a remote test run” under **Description**.</span></span>  
  
4.  <span data-ttu-id="1125c-211">对于步骤 8 中，选择默认命名方案。</span><span class="sxs-lookup"><span data-stu-id="1125c-211">For Step 8, select the default naming scheme.</span></span>  
  
5.  <span data-ttu-id="1125c-212">为在步骤 9，**测试执行方法**选择**远程执行**下**控制器**选择的测试控制器计算机并使其余属性保留在**角色**在其默认设置的页。</span><span class="sxs-lookup"><span data-stu-id="1125c-212">For Step 9, under **Test execution method** select **Remote execution**, under **Controller** select the test controller computer and leave the remaining properties on the **Roles** page at their default settings.</span></span>  
  
6.  <span data-ttu-id="1125c-213">步骤 24 选择**运行在默认主机**，选择**托管类型**的**默认**，并在列表视图**在 32 或 64 位进程中运行测试**，选择该选项以**在 64 位计算机上的 64 位进程中运行测试**。</span><span class="sxs-lookup"><span data-stu-id="1125c-213">For Step 24, select the option **to Run in default host**, select a **Host type** of **Default**, and under **Run tests in 32 or 64 bit process**, select the option to **Run tests in 64 bit process on 64 bit machine**.</span></span>  
  
7.  <span data-ttu-id="1125c-214">对于步骤 25 选择**将单个测试标记为失败的执行时间超过**和保留默认值为 30 分钟选择。</span><span class="sxs-lookup"><span data-stu-id="1125c-214">For Step 25, select **Mark an individual test as failed if its execution time exceeds** and leave the default value of 30 minutes selected.</span></span>  
  
8.  <span data-ttu-id="1125c-215">对于步骤 27b，选中的复选框**的对测试目录中的程序集使用加载上下文**，然后单击**另存为**。</span><span class="sxs-lookup"><span data-stu-id="1125c-215">For Step 27b, select the check box for **Use the Load Context for assemblies in the test directory**, and then click **Save As**.</span></span>  
  
9. <span data-ttu-id="1125c-216">在**另存为**对话框框中，确认名称**BizTalkLoadTest**旁边输入**文件名**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="1125c-216">In the **Save As** dialog box, verify that the name **BizTalkLoadTest** is entered next to **File name**, and click **Save**.</span></span> <span data-ttu-id="1125c-217">现在，您已添加到你的解决方案创建测试设置文件。</span><span class="sxs-lookup"><span data-stu-id="1125c-217">You have now added a test settings file to your solution.</span></span>