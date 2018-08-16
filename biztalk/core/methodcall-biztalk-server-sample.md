---
title: MethodCall （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, calling
- examples, orchestrations
- orchestrations, methods
ms.assetid: 6bdc72da-9478-403a-b706-3089b7374ac7
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ef3869161c699c48648bc0c22f1d9f40c9bde73
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986865"
---
# <a name="methodcall-biztalk-server-sample"></a><span data-ttu-id="f29a2-102">MethodCall （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="f29a2-102">MethodCall (BizTalk Server Sample)</span></span>
<span data-ttu-id="f29a2-103">MethodCall 示例演示如何从 BizTalk Server 业务流程调用基于 .NET 的方法。</span><span class="sxs-lookup"><span data-stu-id="f29a2-103">The MethodCall sample demonstrates how to call a .NET-based method from a BizTalk Server orchestration.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="f29a2-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="f29a2-104">What This Sample Does</span></span>  
 <span data-ttu-id="f29a2-105">本示例通过下列步骤与基于 .NET 的方法交互：</span><span class="sxs-lookup"><span data-stu-id="f29a2-105">This sample interacts with a .NET-based method using the following sequence of steps:</span></span>  

1. <span data-ttu-id="f29a2-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程从 In 文件夹中检索 XML 输入文件。</span><span class="sxs-lookup"><span data-stu-id="f29a2-106">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration retrieves an XML input file from the In folder.</span></span> <span data-ttu-id="f29a2-107">此文件包含想要数学库执行的加法或减法的信息。</span><span class="sxs-lookup"><span data-stu-id="f29a2-107">This file contains information about an addition or subtraction you want the math library to perform.</span></span>  

2. <span data-ttu-id="f29a2-108">业务流程调用所包含的数学库来执行 XML 输入文件中指定的加法或减法。</span><span class="sxs-lookup"><span data-stu-id="f29a2-108">The orchestration calls the included math library to perform the addition or subtraction specified in the XML input file.</span></span>  

3. <span data-ttu-id="f29a2-109">相应的数学库方法，要么**外**或**Subtract**，执行所请求的计算，并将结果打包为一个 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="f29a2-109">The appropriate math library method, either **Add** or **Subtract**, performs the requested calculation and packages the result as an XML document.</span></span>  

4. <span data-ttu-id="f29a2-110">业务流程将结果 .xml 文件放入 Out 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f29a2-110">The orchestration places the resulting .xml file in the Out folder.</span></span>  

## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="f29a2-111">此示例设计方式和原因</span><span class="sxs-lookup"><span data-stu-id="f29a2-111">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="f29a2-112">本示例演示以下功能：</span><span class="sxs-lookup"><span data-stu-id="f29a2-112">This sample demonstrates the following functionalities:</span></span>  

-   <span data-ttu-id="f29a2-113">在业务流程中利用已升级的属性。</span><span class="sxs-lookup"><span data-stu-id="f29a2-113">Leveraging the promoted properties in an orchestration.</span></span> <span data-ttu-id="f29a2-114">InputSchema.xsd 中的三个元素已升级为可分辨字段。</span><span class="sxs-lookup"><span data-stu-id="f29a2-114">The three elements in InputSchema.xsd are promoted as distinguished fields.</span></span> <span data-ttu-id="f29a2-115">业务流程接收到输入消息时，会获得这三个字段的值并将它们分配给在业务流程中声明了的相应变量。</span><span class="sxs-lookup"><span data-stu-id="f29a2-115">When the orchestration receives the input message, it gets the values of these three fields and assigns them to the corresponding variables declared in the orchestration.</span></span>  

-   <span data-ttu-id="f29a2-116">使用**判定**形状表示业务流程中的"-if-then-else"逻辑。</span><span class="sxs-lookup"><span data-stu-id="f29a2-116">Using the **Decide** shape to express "if-then-else" logic in an orchestration.</span></span> <span data-ttu-id="f29a2-117">业务流程将可分辨字段的值分配给内部变量后，会进入**判定**形状中，以检查是否应执行加法还是减法。</span><span class="sxs-lookup"><span data-stu-id="f29a2-117">After the orchestration assigns the values of distinguished fields to internal variables, it enters the **Decide** shape to check whether an addition or subtraction should be performed.</span></span> <span data-ttu-id="f29a2-118">如果不需要执行任何操作，业务流程将终止。</span><span class="sxs-lookup"><span data-stu-id="f29a2-118">If no operation needs to be performed, the orchestration terminates.</span></span>  

-   <span data-ttu-id="f29a2-119">从业务流程调用外部程序集。</span><span class="sxs-lookup"><span data-stu-id="f29a2-119">Calling an external assembly from an orchestration.</span></span> <span data-ttu-id="f29a2-120">如果要执行加法，业务流程将调用外部 C# 程序集并传入两个参数以执行加法。</span><span class="sxs-lookup"><span data-stu-id="f29a2-120">If an addition is to be performed, the orchestration calls an external C# assembly and passes in two parameters to perform the addition.</span></span> <span data-ttu-id="f29a2-121">该过程同样适用于减法。</span><span class="sxs-lookup"><span data-stu-id="f29a2-121">The same procedures apply to a subtraction.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="f29a2-122">您需要将程序集安装到全局程序集缓存中，然后才能从业务流程调用它，否则运行期间将收到 XLANG 错误。</span><span class="sxs-lookup"><span data-stu-id="f29a2-122">You need to install the assembly to the global assembly cache before you can call it from the orchestration; otherwise you will receive an XLANG error during run time.</span></span>  

-   <span data-ttu-id="f29a2-123">使用**消息赋值**形状以构造输出消息。</span><span class="sxs-lookup"><span data-stu-id="f29a2-123">Using the **Message Assignment** shape to construct the output message.</span></span>  

-   <span data-ttu-id="f29a2-124">通过将以下代码放入表达式形状来调试业务流程：</span><span class="sxs-lookup"><span data-stu-id="f29a2-124">Debugging the orchestration by putting the following code in the Expression shape:</span></span>  

    ```  
    System.Diagnostics.Debug.WriteLine(iResult);  
    ```  

     <span data-ttu-id="f29a2-125">您也可以使用如下代码将结果写入事件日志中：</span><span class="sxs-lookup"><span data-stu-id="f29a2-125">You can also write the result to the event log by using:</span></span>  

    ```  
    System.Diagnostics.EventLog.WriteEntry("MethodCall SDK Sample Debug", System.String.Format("Result = {0}", iResult);  
    ```  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="f29a2-126">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="f29a2-126">Where to Find This Sample</span></span>  
 <span data-ttu-id="f29a2-127">\<*示例路径*\>\Orchestrations\MethodCall\\</span><span class="sxs-lookup"><span data-stu-id="f29a2-127">\<*Samples Path*\>\Orchestrations\MethodCall\\</span></span>  

 <span data-ttu-id="f29a2-128">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="f29a2-128">The following table shows the files in this sample and describes their purpose.</span></span>  


|                                          <span data-ttu-id="f29a2-129">文件</span><span class="sxs-lookup"><span data-stu-id="f29a2-129">File(s)</span></span>                                           |                                                                                           <span data-ttu-id="f29a2-130">Description</span><span class="sxs-lookup"><span data-stu-id="f29a2-130">Description</span></span>                                                                                            |
|--------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                        <span data-ttu-id="f29a2-131">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="f29a2-131">Cleanup.bat</span></span>                                         | <span data-ttu-id="f29a2-132">用于取消部署程序集并从全局程序集缓存中删除这些程序集。</span><span class="sxs-lookup"><span data-stu-id="f29a2-132">Used to undeploy assemblies and remove them from the global assembly cache.</span></span> <span data-ttu-id="f29a2-133">删除发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="f29a2-133">Removes send and receive ports.</span></span> <span data-ttu-id="f29a2-134">根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="f29a2-134">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span> |
|                                         <span data-ttu-id="f29a2-135">Input.xml</span><span class="sxs-lookup"><span data-stu-id="f29a2-135">Input.xml</span></span>                                          |                                                                                        <span data-ttu-id="f29a2-136">示例输入文件。</span><span class="sxs-lookup"><span data-stu-id="f29a2-136">Sample input file.</span></span>                                                                                        |
|                                         <span data-ttu-id="f29a2-137">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="f29a2-137">Setup.bat</span></span>                                          |                                                                            <span data-ttu-id="f29a2-138">用于生成和初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="f29a2-138">Used to build and initialize this sample.</span></span>                                                                             |
| <span data-ttu-id="f29a2-139">在 \MathLibrary 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="f29a2-139">In the \MathLibrary folder:</span></span><br /><br /> <span data-ttu-id="f29a2-140">AssemblyInfo.cs、MathHelper.cs 和 MathLibrary.csproj</span><span class="sxs-lookup"><span data-stu-id="f29a2-140">AssemblyInfo.cs, MathHelper.cs, MathLibrary.csproj</span></span> |                                                                <span data-ttu-id="f29a2-141">本示例使用的数学库的项目文件和源文件。</span><span class="sxs-lookup"><span data-stu-id="f29a2-141">Project and source files for the math library used by this sample.</span></span>                                                                |
|       <span data-ttu-id="f29a2-142">在 \MethodCallSample 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="f29a2-142">In the \MethodCallSample folder:</span></span><br /><br /> <span data-ttu-id="f29a2-143">InputSchema.xsd、OutputSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="f29a2-143">InputSchema.xsd, OutputSchema.xsd</span></span>       |                                                                    <span data-ttu-id="f29a2-144">分别为输入和输出 .xml 文件的架构。</span><span class="sxs-lookup"><span data-stu-id="f29a2-144">Schemas for the input and output .xml files, respectively.</span></span>                                                                    |
| <span data-ttu-id="f29a2-145">在 \MethodCallSample 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="f29a2-145">In the \MethodCallSample folder:</span></span><br /><br /> <span data-ttu-id="f29a2-146">MethodCallSample.btproj、MethodCallSample.sln</span><span class="sxs-lookup"><span data-stu-id="f29a2-146">MethodCallSample.btproj, MethodCallSample.sln</span></span> |                                                                           <span data-ttu-id="f29a2-147">本示例的项目文件和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="f29a2-147">Project and solution files for this sample.</span></span>                                                                            |
|          <span data-ttu-id="f29a2-148">在 \MethodCallSample 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="f29a2-148">In the \MethodCallSample folder:</span></span><br /><br /> <span data-ttu-id="f29a2-149">MethodCallSampleBinding.xml</span><span class="sxs-lookup"><span data-stu-id="f29a2-149">MethodCallSampleBinding.xml</span></span>          |                                                                          <span data-ttu-id="f29a2-150">用于如端口绑定之类的自动化设置。</span><span class="sxs-lookup"><span data-stu-id="f29a2-150">Used for automated setup such as port binding.</span></span>                                                                          |
|             <span data-ttu-id="f29a2-151">在 \MethodCallSample 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="f29a2-151">In the \MethodCallSample folder:</span></span><br /><br /> <span data-ttu-id="f29a2-152">MethodCallService.odx</span><span class="sxs-lookup"><span data-stu-id="f29a2-152">MethodCallService.odx</span></span>             |                <span data-ttu-id="f29a2-153">调用数学库以执行所请求的计算的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程。</span><span class="sxs-lookup"><span data-stu-id="f29a2-153">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration that calls the math library to perform the requested calculation.</span></span>                |

## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="f29a2-154">生成并初始化本示例</span><span class="sxs-lookup"><span data-stu-id="f29a2-154">Building and Initializing This Sample</span></span>  

#### <a name="to-build-and-initialize-the-methodcall-sample"></a><span data-ttu-id="f29a2-155">生成并初始化 MethodCall 示例</span><span class="sxs-lookup"><span data-stu-id="f29a2-155">To build and initialize the MethodCall sample</span></span>  

1. <span data-ttu-id="f29a2-156">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="f29a2-156">In a command window, navigate to the following folder:</span></span>  

    <span data-ttu-id="f29a2-157">\<*示例路径*\>\Orchestrations\MethodCall</span><span class="sxs-lookup"><span data-stu-id="f29a2-157">\<*Samples Path*\>\Orchestrations\MethodCall</span></span>  

2. <span data-ttu-id="f29a2-158">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f29a2-158">Run the file Setup.bat, which performs the following actions:</span></span>  

   - <span data-ttu-id="f29a2-159">在 MethodCall 文件夹中，为本示例创建输入 (In) 和输出 (Out) 文件夹。</span><span class="sxs-lookup"><span data-stu-id="f29a2-159">Creates the input (In) and output (Out) folders for this sample in the MethodCall folder.</span></span>  

   - <span data-ttu-id="f29a2-160">编译[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]项目对于此示例，并部署生成的程序集。</span><span class="sxs-lookup"><span data-stu-id="f29a2-160">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample, and deploys the resulting assemblies.</span></span>  

   - <span data-ttu-id="f29a2-161">创建 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置、发送和接收端口，并将它们绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="f29a2-161">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports to the orchestration.</span></span>  

   - <span data-ttu-id="f29a2-162">启用接收位置并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="f29a2-162">Enables the receive location, and starts the send port.</span></span> <span data-ttu-id="f29a2-163">登记并启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="f29a2-163">Enlists and starts orchestration.</span></span>  

> [!NOTE]
>  <span data-ttu-id="f29a2-164">在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="f29a2-164">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  

## <a name="running-this-sample"></a><span data-ttu-id="f29a2-165">运行本示例</span><span class="sxs-lookup"><span data-stu-id="f29a2-165">Running This Sample</span></span>  

#### <a name="to-run-the-methodcall-sample"></a><span data-ttu-id="f29a2-166">运行 MethodCall 示例</span><span class="sxs-lookup"><span data-stu-id="f29a2-166">To run the MethodCall sample</span></span>  

1.  <span data-ttu-id="f29a2-167">将文件 Input.xml 的副本粘贴到 In 文件夹。</span><span class="sxs-lookup"><span data-stu-id="f29a2-167">Paste a copy of the file Input.xml into the In folder.</span></span>  

2.  <span data-ttu-id="f29a2-168">查看在 Out 文件夹中创建的 .xml 文件。</span><span class="sxs-lookup"><span data-stu-id="f29a2-168">Observe the .xml file created in the Out folder.</span></span> <span data-ttu-id="f29a2-169">此文件包含请求的加法或减法的计算结果。</span><span class="sxs-lookup"><span data-stu-id="f29a2-169">This file contains the result of the requested addition or subtraction calculation.</span></span> <span data-ttu-id="f29a2-170">此文件的名称的格式\< *MessageID*\>.xml，其中*\<MessageID\>* 生成的 GUID 来唯一标识消息.</span><span class="sxs-lookup"><span data-stu-id="f29a2-170">The format of the name of this file is \<*MessageID*\>.xml, where *\<MessageID\>* is the GUID generated to uniquely identify the message.</span></span>  

3.  <span data-ttu-id="f29a2-171">您可以修改输入文件以请求不同的加法或减法计算。</span><span class="sxs-lookup"><span data-stu-id="f29a2-171">You can modify the input file to request different addition or subtraction calculations.</span></span>  

## <a name="uninstalling-this-sample"></a><span data-ttu-id="f29a2-172">卸载本示例</span><span class="sxs-lookup"><span data-stu-id="f29a2-172">Uninstalling This Sample</span></span>  

#### <a name="to-uninstall-the-methodcall-sample"></a><span data-ttu-id="f29a2-173">卸载 MethodCall 示例</span><span class="sxs-lookup"><span data-stu-id="f29a2-173">To uninstall the MethodCall sample</span></span>  

1. <span data-ttu-id="f29a2-174">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，将目录更改 (**cd**) 对\<*示例路径*\>\Orchestrations\MethodCall\\。</span><span class="sxs-lookup"><span data-stu-id="f29a2-174">At a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, change directory (**cd**) to \<*Samples Path*\>\Orchestrations\MethodCall\\.</span></span>  

2. <span data-ttu-id="f29a2-175">运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="f29a2-175">Run Cleanup.bat.</span></span>  

## <a name="see-also"></a><span data-ttu-id="f29a2-176">请参阅</span><span class="sxs-lookup"><span data-stu-id="f29a2-176">See Also</span></span>  
 [<span data-ttu-id="f29a2-177">业务流程（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="f29a2-177">Orchestrations (BizTalk Server Samples Folder)</span></span>](../core/orchestrations-biztalk-server-samples-folder.md)