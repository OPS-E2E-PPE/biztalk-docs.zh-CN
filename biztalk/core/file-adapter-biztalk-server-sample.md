---
title: 文件适配器 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, File adapters
- File adapters, examples
ms.assetid: d59cecb4-6353-44d5-b8d6-316446758536
caps.latest.revision: 46
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2260c29394227c9bcd905f0b87b062a35ee27e1f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345577"
---
# <a name="file-adapter-biztalk-server-sample"></a><span data-ttu-id="42c3e-102">文件适配器 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="42c3e-102">File Adapter (BizTalk Server Sample)</span></span>
<span data-ttu-id="42c3e-103">文件适配器示例用 Microsoft Visual C#.NET 能够使用 Microsoft BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="42c3e-103">The File Adapter sample is written in Microsoft Visual C# .NET to work with Microsoft BizTalk Server.</span></span> <span data-ttu-id="42c3e-104">它提供了代码生成动态或静态适配器。</span><span class="sxs-lookup"><span data-stu-id="42c3e-104">It provides code to build either a dynamic or a static adapter.</span></span>  <span data-ttu-id="42c3e-105">但是，以下过程仅简要介绍静态适配器。</span><span class="sxs-lookup"><span data-stu-id="42c3e-105">However, the following procedure only outlines the static adapter.</span></span> <span data-ttu-id="42c3e-106">静态适配器是使用一组静态的架构和任何自定义用户界面的适配器。</span><span class="sxs-lookup"><span data-stu-id="42c3e-106">A static adapter is an adapter with a static set of schemas and no custom user interface.</span></span> <span data-ttu-id="42c3e-107">动态适配器具有自定义用户界面和可能动态架构集合。</span><span class="sxs-lookup"><span data-stu-id="42c3e-107">A dynamic adapter has a custom user interface and potentially a dynamic set of schemas.</span></span> <span data-ttu-id="42c3e-108">静态和动态适配器使用添加适配器向导以将其架构添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="42c3e-108">Both static and dynamic adapters use the Add Adapter Wizard to add their schemas to a BizTalk project.</span></span>  

> [!NOTE]
>  <span data-ttu-id="42c3e-109">文件适配器示例中不附带有 BizTalk Server 的本机 FILE 适配器相同。</span><span class="sxs-lookup"><span data-stu-id="42c3e-109">The File adapter sample is not the same as the native FILE adapter that ships with BizTalk Server.</span></span> <span data-ttu-id="42c3e-110">因此当使用此示例选择的传输类型选择"静态"而不是文件。</span><span class="sxs-lookup"><span data-stu-id="42c3e-110">Thus when selecting the transport type in using this sample select "static" instead of FILE.</span></span>  

 <span data-ttu-id="42c3e-111">自定义用户界面并可能具有动态架构集合的动态适配器需要适配器管理方面中的其他代码。</span><span class="sxs-lookup"><span data-stu-id="42c3e-111">The dynamic adapter with a custom user interface and potentially dynamic set of schemas will require additional code in the adapter management side.</span></span> <span data-ttu-id="42c3e-112">若要更好地了解使用动态架构集合，请参阅[动态设计时适配器配置](../core/dynamic-design-time-adapter-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="42c3e-112">To better understand use of the dynamic set of schemas, see [Dynamic Design-Time Adapter Configuration](../core/dynamic-design-time-adapter-configuration.md).</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="42c3e-113">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="42c3e-113">What This Sample Does</span></span>  
 <span data-ttu-id="42c3e-114">示例适配器从文件文件夹中复制文件、 将提交给 BizTalk 作为消息或接收的消息从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和将放入一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="42c3e-114">The sample adapter copies files from a file folder, submits to BizTalk as messages, or takes messages from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and drops to a file folder.</span></span> <span data-ttu-id="42c3e-115">它提供了代码生成动态或静态适配器;但是，以下过程仅简要介绍静态适配器。</span><span class="sxs-lookup"><span data-stu-id="42c3e-115">It provides code to build either a dynamic or a static adapter; however, the following procedure only outlines the static adapter.</span></span> <span data-ttu-id="42c3e-116">静态适配器是使用一组静态的架构和任何自定义用户界面的适配器。</span><span class="sxs-lookup"><span data-stu-id="42c3e-116">A static adapter is an adapter with a static set of schemas and no custom user interface.</span></span> <span data-ttu-id="42c3e-117">动态适配器具有自定义用户界面和可能动态架构集合。</span><span class="sxs-lookup"><span data-stu-id="42c3e-117">A dynamic adapter has a custom user interface and potentially a dynamic set of schemas.</span></span> <span data-ttu-id="42c3e-118">静态和动态适配器使用添加适配器向导以将其架构添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="42c3e-118">Both static and dynamic adapters use the Add Adapter Wizard to add their schemas to a BizTalk project.</span></span>  

 <span data-ttu-id="42c3e-119">示例文件适配器可用作模板在其上创建其他自定义适配器。</span><span class="sxs-lookup"><span data-stu-id="42c3e-119">You can use the sample file adapter as a template on which to create other custom adapters.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="42c3e-120">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="42c3e-120">Where to Find This Sample</span></span>  
 <span data-ttu-id="42c3e-121">\<*Samples Path*\>**\AdaptersDevelopment\File Adapter**</span><span class="sxs-lookup"><span data-stu-id="42c3e-121">\<*Samples Path*\>**\AdaptersDevelopment\File Adapter**</span></span>  

> [!NOTE]
>  <span data-ttu-id="42c3e-122">默认位置\<*示例路径*\>是 *%programfiles%* \Microsoft BizTalk Server\SDK\Samples 时运行 32 位的计算机上安装 BizTalk ServerWindows 版本。</span><span class="sxs-lookup"><span data-stu-id="42c3e-122">The default location for \<*Samples Path*\> is *%ProgramFiles%* \Microsoft BizTalk Server\SDK\Samples when BizTalk Server is installed on a computer running a 32-bit version of Windows.</span></span> <span data-ttu-id="42c3e-123">默认位置\<*示例路径*\>是 *%programfiles （x86） %* \Microsoft BizTalk Server\SDK\Samples 时运行 64 的计算机上安装 BizTalk Server位版本的 Windows。</span><span class="sxs-lookup"><span data-stu-id="42c3e-123">The default location for \<*Samples Path*\> is *%ProgramFiles(x86)%* \Microsoft BizTalk Server\SDK\Samples when BizTalk Server is installed on a computer running a 64-bit version of Windows.</span></span> <span data-ttu-id="42c3e-124">若要确定与关联的值 *%programfiles%* 或 *%programfiles （x86） %* 环境变量类型**echo %programfiles%** 或**echo %Programfiles （x86） %** 在命令提示符，然后按 ENTER 键。</span><span class="sxs-lookup"><span data-stu-id="42c3e-124">To determine the values associated with the *%ProgramFiles%* or *%ProgramFiles(x86)%* environment variables type **echo %ProgramFiles%** or **echo %ProgramFiles(x86)%** at a command prompt and press ENTER.</span></span> <span data-ttu-id="42c3e-125">如果在 64 位操作系统上运行此示例，您需要更改中的任何.reg 文件中的所有引用 **%programfiles%** 到 **%programfiles （x86） %** 之前正在运行的.reg 文件。</span><span class="sxs-lookup"><span data-stu-id="42c3e-125">If running this sample on a 64-bit operating system, you will need to change all references in any of the .reg files from **%ProgramFiles%** to **%ProgramFiles(x86)%** before running the .reg files.</span></span>  

 <span data-ttu-id="42c3e-126">下表显示在此示例中的文件，并说明了其用途。</span><span class="sxs-lookup"><span data-stu-id="42c3e-126">The following tables show the files in this sample and describe their purpose.</span></span>  

|<span data-ttu-id="42c3e-127">\File adapter 文件</span><span class="sxs-lookup"><span data-stu-id="42c3e-127">\File Adapter files</span></span>|<span data-ttu-id="42c3e-128">Description</span><span class="sxs-lookup"><span data-stu-id="42c3e-128">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="42c3e-129">\BizTalk project 文件</span><span class="sxs-lookup"><span data-stu-id="42c3e-129">\BizTalk Project files</span></span>|<span data-ttu-id="42c3e-130">包含适配器管理项目，用于测试示例适配器。</span><span class="sxs-lookup"><span data-stu-id="42c3e-130">Contains the adapter harness project, used to test the sample adapter.</span></span>|  
|<span data-ttu-id="42c3e-131">\Design time 文件</span><span class="sxs-lookup"><span data-stu-id="42c3e-131">\Design Time files</span></span>|<span data-ttu-id="42c3e-132">包含设计时和管理项目 (AdapterManagement.csproj)。</span><span class="sxs-lookup"><span data-stu-id="42c3e-132">Contains the design time and management project (AdapterManagement.csproj).</span></span>|  
|<span data-ttu-id="42c3e-133">\Runtime 文件</span><span class="sxs-lookup"><span data-stu-id="42c3e-133">\Runtime files</span></span>|<span data-ttu-id="42c3e-134">包含运行时文件复制接收和传输项目 (DotNetFile.csproj)。</span><span class="sxs-lookup"><span data-stu-id="42c3e-134">Contains the run-time file-copy receive and transmit projects (DotNetFile.csproj).</span></span>|  
|<span data-ttu-id="42c3e-135">DynamicAdapterManagement.reg</span><span class="sxs-lookup"><span data-stu-id="42c3e-135">DynamicAdapterManagement.reg</span></span>|<span data-ttu-id="42c3e-136">注册示例动态适配器。</span><span class="sxs-lookup"><span data-stu-id="42c3e-136">Registers the sample dynamic adapter.</span></span>|  
|<span data-ttu-id="42c3e-137">Instance.xml</span><span class="sxs-lookup"><span data-stu-id="42c3e-137">Instance.xml</span></span>|<span data-ttu-id="42c3e-138">若要通过文件适配器的示例文件。</span><span class="sxs-lookup"><span data-stu-id="42c3e-138">Sample file to pass through the file adapter.</span></span>|  
|<span data-ttu-id="42c3e-139">StaticAdapterManagement.reg</span><span class="sxs-lookup"><span data-stu-id="42c3e-139">StaticAdapterManagement.reg</span></span>|<span data-ttu-id="42c3e-140">注册示例静态适配器。</span><span class="sxs-lookup"><span data-stu-id="42c3e-140">Registers the sample static adapter.</span></span>|  

|<span data-ttu-id="42c3e-141">\BizTalk Project\Adapter harness 文件</span><span class="sxs-lookup"><span data-stu-id="42c3e-141">\BizTalk Project\Adapter Harness files</span></span>|<span data-ttu-id="42c3e-142">Description</span><span class="sxs-lookup"><span data-stu-id="42c3e-142">Description</span></span>|  
|----------------------------------------------|-----------------|  
|<span data-ttu-id="42c3e-143">AdapterHarness.odx、 AdapterHarness.sln、 AdapterHarnessProject.btproj</span><span class="sxs-lookup"><span data-stu-id="42c3e-143">AdapterHarness.odx, AdapterHarness.sln, AdapterHarnessProject.btproj</span></span>|<span data-ttu-id="42c3e-144">提供了项目、 解决方案和相关的 BizTalk 项目文件。</span><span class="sxs-lookup"><span data-stu-id="42c3e-144">Provides project, solution, and related files for the BizTalk project.</span></span>|  
|<span data-ttu-id="42c3e-145">mySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="42c3e-145">mySchema.xsd</span></span>|<span data-ttu-id="42c3e-146">提供所需的业务流程从适配器的接收部分的 Instance.xml 的架构，以及由业务流程传递给适配器的发送部分的 Instance.xml 的架构。</span><span class="sxs-lookup"><span data-stu-id="42c3e-146">Provides the Instance.xml schema expected by the harness orchestration from the receive part of the adapter, as well as the schema of the Instance.xml handed to the send part of the adapter by the orchestration.</span></span>|  

|<span data-ttu-id="42c3e-147">\Design Time\Adapter 管理文件</span><span class="sxs-lookup"><span data-stu-id="42c3e-147">\Design Time\Adapter Management files</span></span>|<span data-ttu-id="42c3e-148">Description</span><span class="sxs-lookup"><span data-stu-id="42c3e-148">Description</span></span>|  
|---------------------------------------------|-----------------|  
|<span data-ttu-id="42c3e-149">AdapterManagement.cs, AdapterManagement.csproj, AdapterManagement.sln</span><span class="sxs-lookup"><span data-stu-id="42c3e-149">AdapterManagement.cs, AdapterManagement.csproj, AdapterManagement.sln</span></span>|<span data-ttu-id="42c3e-150">项目、 解决方案和适配器设计时的相关的文件。</span><span class="sxs-lookup"><span data-stu-id="42c3e-150">Project, solution, and related files for the adapter design-time.</span></span>|  
|<span data-ttu-id="42c3e-151">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="42c3e-151">AssemblyInfo.cs</span></span>|<span data-ttu-id="42c3e-152">包含此示例的程序集信息。</span><span class="sxs-lookup"><span data-stu-id="42c3e-152">Contains assembly information for this sample.</span></span>|  
|<span data-ttu-id="42c3e-153">CategorySchema2.xml</span><span class="sxs-lookup"><span data-stu-id="42c3e-153">CategorySchema2.xml</span></span>|<span data-ttu-id="42c3e-154">不使用示例适配器。</span><span class="sxs-lookup"><span data-stu-id="42c3e-154">Not used by the sample adapter.</span></span>|  
|<span data-ttu-id="42c3e-155">CategorySchema.xml</span><span class="sxs-lookup"><span data-stu-id="42c3e-155">CategorySchema.xml</span></span>|<span data-ttu-id="42c3e-156">包含静态适配器的服务组织树。</span><span class="sxs-lookup"><span data-stu-id="42c3e-156">Contains the service organization tree for the static adapter.</span></span>|  
|<span data-ttu-id="42c3e-157">DotNetFileResource.resx</span><span class="sxs-lookup"><span data-stu-id="42c3e-157">DotNetFileResource.resx</span></span>|<span data-ttu-id="42c3e-158">包含的资源。</span><span class="sxs-lookup"><span data-stu-id="42c3e-158">Contains resources.</span></span>|  
|<span data-ttu-id="42c3e-159">ReceiveHandler.xsd, ReceiveLocation.xsd</span><span class="sxs-lookup"><span data-stu-id="42c3e-159">ReceiveHandler.xsd, ReceiveLocation.xsd</span></span>|<span data-ttu-id="42c3e-160">包含接收端处理程序和终结点自定义属性架构</span><span class="sxs-lookup"><span data-stu-id="42c3e-160">Contains receive side handler and endpoint custom property schemas</span></span>|  
|<span data-ttu-id="42c3e-161">service1.wsdl</span><span class="sxs-lookup"><span data-stu-id="42c3e-161">service1.wsdl</span></span>|<span data-ttu-id="42c3e-162">包含适配器的操作定义。</span><span class="sxs-lookup"><span data-stu-id="42c3e-162">Contains operation definitions for the adapter.</span></span>|  
|<span data-ttu-id="42c3e-163">TransmitHandler.xsd, TransmitLocation.xsd</span><span class="sxs-lookup"><span data-stu-id="42c3e-163">TransmitHandler.xsd, TransmitLocation.xsd</span></span>|<span data-ttu-id="42c3e-164">包含传输端处理程序和终结点自定义属性架构</span><span class="sxs-lookup"><span data-stu-id="42c3e-164">Contains transmit side handler and endpoint custom property schemas</span></span>|  

|                                                                                                                                                             <span data-ttu-id="42c3e-165">\Runtime 文件</span><span class="sxs-lookup"><span data-stu-id="42c3e-165">\Runtime files</span></span>                                                                                                                                                              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  <span data-ttu-id="42c3e-166">Description</span><span class="sxs-lookup"><span data-stu-id="42c3e-166">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="42c3e-167">DotNetFile.csproj, DotNetFile.sln,</span><span class="sxs-lookup"><span data-stu-id="42c3e-167">DotNetFile.csproj, DotNetFile.sln,</span></span><br /><br /> <span data-ttu-id="42c3e-168">AssemblyInfo.cs、</span><span class="sxs-lookup"><span data-stu-id="42c3e-168">AssemblyInfo.cs,</span></span><br /><br /> <span data-ttu-id="42c3e-169">DotNetFileExceptions.cs, DotNetFileProperties.cs, DotNetFileReceiver.cs, DotNetFileReceiverEndPoint.cs, DotNetFileTransmitter.cs,</span><span class="sxs-lookup"><span data-stu-id="42c3e-169">DotNetFileExceptions.cs, DotNetFileProperties.cs, DotNetFileReceiver.cs, DotNetFileReceiverEndPoint.cs, DotNetFileTransmitter.cs,</span></span><br /><br /> <span data-ttu-id="42c3e-170">DotNetFileTransmitterEndpoint.cs,</span><span class="sxs-lookup"><span data-stu-id="42c3e-170">DotNetFileTransmitterEndpoint.cs,</span></span><br /><br /> <span data-ttu-id="42c3e-171">DotNetFileAsyncTransmitterBatch.cs,</span><span class="sxs-lookup"><span data-stu-id="42c3e-171">DotNetFileAsyncTransmitterBatch.cs,</span></span><br /><br /> <span data-ttu-id="42c3e-172">BatchMessage.cs</span><span class="sxs-lookup"><span data-stu-id="42c3e-172">BatchMessage.cs</span></span> | <span data-ttu-id="42c3e-173">运行时文件复制的文件发送和接收适配器。</span><span class="sxs-lookup"><span data-stu-id="42c3e-173">Files for the run-time file-copy send and receive adapters.</span></span> <span data-ttu-id="42c3e-174">可以修改和保存自定义组件的新名称下的这些文件。</span><span class="sxs-lookup"><span data-stu-id="42c3e-174">You can modify and save these files under a new name for custom components.</span></span><br /><br /> <span data-ttu-id="42c3e-175">DotNetFile.csproj 和 DotNetFile.sln 是项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="42c3e-175">DotNetFile.csproj and DotNetFile.sln are the project and solution files.</span></span><br /><br /> <span data-ttu-id="42c3e-176">AssemblyInfo.cs 包含本示例的程序集信息。</span><span class="sxs-lookup"><span data-stu-id="42c3e-176">AssemblyInfo.cs contains assembly information for this sample.</span></span><br /><br /> <span data-ttu-id="42c3e-177">DotNetFileReceiver.cs 从接收位置读取文件并将其提交给[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="42c3e-177">DotNetFileReceiver.cs reads the files from the receive locations and submits them to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="42c3e-178">DotNetFileExceptions.cs,implements 代码以在消息处理过程中处理异常</span><span class="sxs-lookup"><span data-stu-id="42c3e-178">DotNetFileExceptions.cs,implements code to handle exceptions during message processing</span></span><br /><br /> <span data-ttu-id="42c3e-179">DotNetFileProperties.cs 包含接收和发送操作的通用属性</span><span class="sxs-lookup"><span data-stu-id="42c3e-179">DotNetFileProperties.cs, contains common properties for both Receive and Send operations</span></span><br /><br /> <span data-ttu-id="42c3e-180">BatchMessage.cs 实现批处理消息传送。</span><span class="sxs-lookup"><span data-stu-id="42c3e-180">BatchMessage.cs, implements batch messaging.</span></span><br /><br /> <span data-ttu-id="42c3e-181">类 DotNetFileReceiverEndPoint.cs，相应对接收位置/URI。</span><span class="sxs-lookup"><span data-stu-id="42c3e-181">DotNetFileReceiverEndPoint.cs, is a class corresponding to a Receive Location/URI.</span></span>  <span data-ttu-id="42c3e-182">它负责轮询给定的文件夹以查看新消息</span><span class="sxs-lookup"><span data-stu-id="42c3e-182">It handles polling the given folder for new messages</span></span><br /><br /> <span data-ttu-id="42c3e-183">DotNetFileTransmitter.cs 是用于 DotNetFile 发送适配器的单一实例类。</span><span class="sxs-lookup"><span data-stu-id="42c3e-183">DotNetFileTransmitter.cs is a singleton class for DotNetFile send adapter.</span></span> <span data-ttu-id="42c3e-184">所有消息，转到此适配器类型的各个发送端口都都将通过此类</span><span class="sxs-lookup"><span data-stu-id="42c3e-184">All the messages, going to various send ports of this adapter type go through this class</span></span><br /><br /> <span data-ttu-id="42c3e-185">DotNetFileTransmitterEndpoint.cs,handles 传输消息。</span><span class="sxs-lookup"><span data-stu-id="42c3e-185">DotNetFileTransmitterEndpoint.cs,handles transmitting messages.</span></span> |

|<span data-ttu-id="42c3e-186">\SDK\Samples\AdaptersDevelopment\BaseAdapter\v1.0.2 files</span><span class="sxs-lookup"><span data-stu-id="42c3e-186">\SDK\Samples\AdaptersDevelopment\BaseAdapter\v1.0.2 files</span></span>|<span data-ttu-id="42c3e-187">Description</span><span class="sxs-lookup"><span data-stu-id="42c3e-187">Description</span></span>|  
|--------------------------------------------------------------------|-----------------|  
|<span data-ttu-id="42c3e-188">Adapter.cs、 AdapterException.cs、 AsyncTransmitter.cs、 batch.cs、 ConfigProperties.cs、 ControlledTermination.cs、 IManageEndpoints.cs、 Receiver.cs、 ReceiverEndpoint.cs</span><span class="sxs-lookup"><span data-stu-id="42c3e-188">Adapter.cs, AdapterException.cs, AsyncTransmitter.cs, batch.cs, ConfigProperties.cs, ControlledTermination.cs, IManageEndpoints.cs, Receiver.cs, ReceiverEndpoint.cs</span></span>|<span data-ttu-id="42c3e-189">提供构成基本适配器类。</span><span class="sxs-lookup"><span data-stu-id="42c3e-189">Provides classes that constitute the Base Adapter.</span></span> <span data-ttu-id="42c3e-190">可以使用这些来创建你自己的适配器。</span><span class="sxs-lookup"><span data-stu-id="42c3e-190">You can use these to create your own adapters.</span></span>|  

## <a name="how-to-use-this-sample"></a><span data-ttu-id="42c3e-191">如何使用此示例</span><span class="sxs-lookup"><span data-stu-id="42c3e-191">How to Use This Sample</span></span>  
 <span data-ttu-id="42c3e-192">使用作为模板在其上创建其他自定义适配器的示例文件适配器。</span><span class="sxs-lookup"><span data-stu-id="42c3e-192">Use the sample file adapter as a template on which to create other custom adapters.</span></span>  

## <a name="building-this-sample"></a><span data-ttu-id="42c3e-193">生成本示例</span><span class="sxs-lookup"><span data-stu-id="42c3e-193">Building This Sample</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="42c3e-194">如果 BizTalk 安装的是 64 位或修改安装位置，OutboundAssemblyPath、 InboundAssemblyPath、 AdapterMgmtAssemblyPath 需要相应地更改。</span><span class="sxs-lookup"><span data-stu-id="42c3e-194">If the BizTalk installation is 64-bit or the location of installation is modified, OutboundAssemblyPath, InboundAssemblyPath, AdapterMgmtAssemblyPath would need to be changed accordingly.</span></span>  

 <span data-ttu-id="42c3e-195">使用以下过程生成并初始化文件适配器示例。</span><span class="sxs-lookup"><span data-stu-id="42c3e-195">Use the following procedures to build and initialize the File Adapter sample.</span></span>  

#### <a name="to-create-a-strong-name-key-for-the-dotnetfileadapter-projects-and-the-base-adapter-project"></a><span data-ttu-id="42c3e-196">若要创建强名称密钥为 DotNetFileAdapter 项目和基本适配器项目</span><span class="sxs-lookup"><span data-stu-id="42c3e-196">To create a strong name key for the DotNetFileAdapter projects and the Base Adapter project</span></span>  

1.  <span data-ttu-id="42c3e-197">启动**Visual Studio 命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-197">Start **Visual Studio Command Prompt**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="42c3e-198">以管理员身份运行命令提示符。</span><span class="sxs-lookup"><span data-stu-id="42c3e-198">Run the command prompt as an Administrator.</span></span>  

2.  <span data-ttu-id="42c3e-199">将当前目录更改为\<*示例路径*\>**\AdaptersDevelopment\BaseAdapter\v1.0.2**目录。</span><span class="sxs-lookup"><span data-stu-id="42c3e-199">Change the current directory to the \<*Samples Path*\>**\AdaptersDevelopment\BaseAdapter\v1.0.2** directory.</span></span>  

3.  <span data-ttu-id="42c3e-200">在命令提示符处，键入**sn – k BaseAdapter.snk** ，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="42c3e-200">At the command prompt, type **sn –k BaseAdapter.snk** and then press ENTER.</span></span> <span data-ttu-id="42c3e-201">如果以前运行过其他示例，可能已经存在此.snk 文件。</span><span class="sxs-lookup"><span data-stu-id="42c3e-201">This .snk file may already exist as a result of other samples being run previously.</span></span> <span data-ttu-id="42c3e-202">如果是这样，您可以直接转到步骤 4 和跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="42c3e-202">If so, you can go right to step 4 and skip this step.</span></span>  

4.  <span data-ttu-id="42c3e-203">将当前目录更改为\<*示例路径*\>\\**AdaptersDevelopment\File Adapter\Runtime**目录。</span><span class="sxs-lookup"><span data-stu-id="42c3e-203">Change the current directory to the \<*Samples Path*\>\\**AdaptersDevelopment\File Adapter\Runtime** directory.</span></span>  

5.  <span data-ttu-id="42c3e-204">在命令提示符处，键入**sn – k DotNetFileAdapter.snk** ，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="42c3e-204">At the command prompt, type **sn –k DotNetFileAdapter.snk** and then press ENTER.</span></span>  

6.  <span data-ttu-id="42c3e-205">在命令提示符处，键入**退出**，然后按 ENTER 以关闭命令提示符窗口。</span><span class="sxs-lookup"><span data-stu-id="42c3e-205">At the command prompt, type **exit** and then press ENTER to close the command prompt window.</span></span>  

#### <a name="to-build-the-receiver-run-time-project"></a><span data-ttu-id="42c3e-206">若要生成接收器运行时项目</span><span class="sxs-lookup"><span data-stu-id="42c3e-206">To build the receiver run-time project</span></span>  

1.  <span data-ttu-id="42c3e-207">单击**启动**，依次指向**所有程序**，指向**附件**，然后单击**Windows 资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-207">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Windows Explorer**.</span></span>  

2.  <span data-ttu-id="42c3e-208">导航到\<*示例路径*\>**"\AdaptersDevelopment\File Adapter\Runtime"** 目录中，然后再双击**DotNetFile.sln**.</span><span class="sxs-lookup"><span data-stu-id="42c3e-208">Navigate to the \<*Samples Path*\>**”\AdaptersDevelopment\File Adapter\Runtime”** directory, and then double-click **DotNetFile.sln**.</span></span>  

3.  <span data-ttu-id="42c3e-209">若要重新生成适配器接收器运行时项目，在解决方案资源管理器，右键单击**DotNetFile**，然后单击**重新生成**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-209">To rebuild the Adapter Receiver run-time project, in Solution Explorer, right-click **DotNetFile**, and then click **Rebuild**.</span></span>  

4.  <span data-ttu-id="42c3e-210">从**文件**菜单上，单击**退出**以关闭 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="42c3e-210">From the **File** menu, click **Exit** to close Visual Studio.</span></span>  

#### <a name="to-build-the-adapter-design-time-project"></a><span data-ttu-id="42c3e-211">若要生成适配器设计时项目</span><span class="sxs-lookup"><span data-stu-id="42c3e-211">To build the adapter design-time project</span></span>  

1.  <span data-ttu-id="42c3e-212">在 Windows 资源管理器，导航到\<*示例路径*\>**"\AdaptersDevelopment\File Adapter\Design Time\Adapter Management"** 目录，然后再双击**AdapterManagement.sln**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-212">In Windows Explorer, navigate to the \<*Samples Path*\>**”\AdaptersDevelopment\File Adapter\Design Time\Adapter Management”** directory, and then double-click **AdapterManagement.sln**.</span></span>  

2.  <span data-ttu-id="42c3e-213">在解决方案资源管理器中右键单击**AdapterManagement**，然后单击**重新生成**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-213">In Solution Explorer, right-click **AdapterManagement**, and then click **Rebuild**.</span></span>  

3.  <span data-ttu-id="42c3e-214">从**文件**菜单上，单击**退出**以关闭 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="42c3e-214">From the **File** menu, click **Exit** to close Visual Studio.</span></span>  

#### <a name="to-register-the-sample-static-adapter"></a><span data-ttu-id="42c3e-215">若要注册示例静态适配器</span><span class="sxs-lookup"><span data-stu-id="42c3e-215">To register the sample static adapter</span></span>  

1. <span data-ttu-id="42c3e-216">在 Windows 资源管理器，导航到\<*示例路径*\>**"\AdaptersDevelopment\File 适配器"** 目录。</span><span class="sxs-lookup"><span data-stu-id="42c3e-216">In Windows Explorer, navigate to the \<*Samples Path*\>**”\AdaptersDevelopment\File Adapter”** directory.</span></span>  

2. <span data-ttu-id="42c3e-217">若要将示例适配器添加到注册表中，双击**StaticAdapterManagement.reg**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-217">To add the sample adapter to the registry, double-click **StaticAdapterManagement.reg**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="42c3e-218">StaticAdapterManagement.reg 包含硬编码路径为 C:\Program Files\Microsoft BizTalk Server\\。</span><span class="sxs-lookup"><span data-stu-id="42c3e-218">StaticAdapterManagement.reg includes hard-coded paths to C:\Program Files\Microsoft BizTalk Server\\.</span></span> <span data-ttu-id="42c3e-219">如果未安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在 %ProgramFiles%\Microsoft BizTalk Server\ 目录下，如果从 BizTalk Server 2009 或 BizTalk Server 2006 R2 升级到 BizTalk Server 安装或正在运行的计算机上安装 BizTalk Server64 位版本的 Windows，必须修改文件 StaticAdapterManagement.reg 使用相应的路径。</span><span class="sxs-lookup"><span data-stu-id="42c3e-219">If you did not install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the %ProgramFiles%\Microsoft BizTalk Server\ directory, if you upgraded your BizTalk Server installation from BizTalk Server 2009 or BizTalk Server 2006 R2, or if you installed BizTalk Server on a computer that is running a 64-bit version of Windows, you must modify the file StaticAdapterManagement.reg with the appropriate paths.</span></span> <span data-ttu-id="42c3e-220">默认情况下，BizTalk Server 安装到 %programfiles(x86) %\Microsoft 运行 Windows 的 64 位版本的计算机上的 BizTalk Server\ 目录。</span><span class="sxs-lookup"><span data-stu-id="42c3e-220">By default, BizTalk Server is installed into the %ProgramFiles(x86)%\Microsoft BizTalk Server\ directory on computers that are running a 64-bit version of Windows.</span></span> <span data-ttu-id="42c3e-221">更新与"揑 InboundAssemblyPath"、"揙 OutboundAssemblyPath"和"AdapterMgmtAssemblyPath"值，使其指向正确的位置的指定文件相关联的路径。</span><span class="sxs-lookup"><span data-stu-id="42c3e-221">Update the paths associated with the "InboundAssemblyPath", "OutboundAssemblyPath" and "AdapterMgmtAssemblyPath" values to point to the correct location of the specified files.</span></span>  
   > 
   > [!IMPORTANT]
   >  <span data-ttu-id="42c3e-222">如果在 64 位计算机上安装 BizTalk，将 HKEY_CLASSES_ROOT\CLSID\ 注册表项的所有实例都更改为 hkey_classes_root\wow6432node\clsid \ 中**StaticAdapterManagement.reg**注册表文件。</span><span class="sxs-lookup"><span data-stu-id="42c3e-222">If you install BizTalk on a 64 bit machine, change all instances of the HKEY_CLASSES_ROOT\CLSID\ registry entry to HKEY_CLASSES_ROOT\Wow6432Node\CLSID\ in the **StaticAdapterManagement.reg** registry file.</span></span>  

3. <span data-ttu-id="42c3e-223">在中**注册表编辑器**对话框中，单击**是**以将示例适配器添加到注册表，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-223">In the **Registry Editor** dialog box, click **Yes** to add the sample adapter to the registry, and then click **OK**.</span></span>  

4. <span data-ttu-id="42c3e-224">若要关闭 Windows 资源管理器，在**文件**菜单上，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-224">To close Windows Explorer, on the **File** menu, click **Close**.</span></span>  

#### <a name="to-install-the-sample-static-adapter"></a><span data-ttu-id="42c3e-225">若要安装示例静态适配器</span><span class="sxs-lookup"><span data-stu-id="42c3e-225">To install the sample static adapter</span></span>  

1. <span data-ttu-id="42c3e-226">单击**启动**，选择**所有程序**，选择[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后选择**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-226">Click **Start**, select **All Programs**, select [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then select **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="42c3e-227">在 BizTalk Server 管理控制台中，单击以展开**BizTalk Server 管理**，单击此项可展开**BizTalk 组**，并单击以展开**平台设置**.</span><span class="sxs-lookup"><span data-stu-id="42c3e-227">In the BizTalk Server Administration console, click to expand **BizTalk Server Administration**, click to expand **BizTalk Group**, and click to expand **Platform Settings**.</span></span>  

3. <span data-ttu-id="42c3e-228">右键单击**适配器**，单击**新建**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-228">Right click **Adapters**, click **New**, and then click **Adapter**.</span></span>  

4. <span data-ttu-id="42c3e-229">在中**添加适配器**对话框框中，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="42c3e-229">In the **Add Adapter** dialog box, do the following.</span></span>  


   |  <span data-ttu-id="42c3e-230">使用此选项</span><span class="sxs-lookup"><span data-stu-id="42c3e-230">Use this</span></span>   |                      <span data-ttu-id="42c3e-231">执行的操作</span><span class="sxs-lookup"><span data-stu-id="42c3e-231">To do this</span></span>                       |
   |-------------|-------------------------------------------------------|
   |  <span data-ttu-id="42c3e-232">**名称**</span><span class="sxs-lookup"><span data-stu-id="42c3e-232">**Name**</span></span>   |                   <span data-ttu-id="42c3e-233">类型**静态**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-233">Type **Static**.</span></span>                    |
   | <span data-ttu-id="42c3e-234">**适配器**</span><span class="sxs-lookup"><span data-stu-id="42c3e-234">**Adapter**</span></span> | <span data-ttu-id="42c3e-235">选择**Static DotNetFile**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="42c3e-235">Select **Static DotNetFile** from the drop-down list.</span></span> |
   | <span data-ttu-id="42c3e-236">**注释**</span><span class="sxs-lookup"><span data-stu-id="42c3e-236">**Comment**</span></span> |               <span data-ttu-id="42c3e-237">类型**示例适配器**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-237">Type **Sample Adapter**.</span></span>                |


5. <span data-ttu-id="42c3e-238">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="42c3e-238">Click **OK**.</span></span>  

    <span data-ttu-id="42c3e-239">该静态适配器现在将显示在 BizTalk 管理控制台右侧窗口中的适配器列表中。</span><span class="sxs-lookup"><span data-stu-id="42c3e-239">The static adapter now appears in the list of adapters in the right window of the BizTalk Administration console.</span></span>  

#### <a name="to-stop-and-restart-the-host-instance"></a><span data-ttu-id="42c3e-240">若要停止并重新启动主机实例</span><span class="sxs-lookup"><span data-stu-id="42c3e-240">To stop and restart the host instance</span></span>  

1. <span data-ttu-id="42c3e-241">单击**启动**，选择**所有程序**，选择[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后选择**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-241">Click **Start**, select **All Programs**, select [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and select **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="42c3e-242">在 BizTalk Server 管理控制台中，单击以展开**BizTalk Server 管理**，单击此项可展开**BizTalk 组**，单击此项可展开**平台设置**然后单击**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-242">In the BizTalk Server Administration console, click to expand **BizTalk Server Administration**, click to expand **BizTalk Group**, click to expand **Platform Settings** and click **Host Instances**.</span></span> <span data-ttu-id="42c3e-243">在右窗格中选择 BizTalkServerApplication。</span><span class="sxs-lookup"><span data-stu-id="42c3e-243">Select the BizTalkServerApplication in the right pane.</span></span>  

3. <span data-ttu-id="42c3e-244">在结果窗格中，右键单击主机实例 （通常情况下，计算机名称），然后依次**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-244">In the results pane, right-click the host instance (typically, the computer name), and then click **Restart**.</span></span>  

### <a name="running-this-sample"></a><span data-ttu-id="42c3e-245">运行本示例</span><span class="sxs-lookup"><span data-stu-id="42c3e-245">Running This Sample</span></span>  

##### <a name="to-run-the-file-adapter-sample"></a><span data-ttu-id="42c3e-246">若要运行文件适配器示例</span><span class="sxs-lookup"><span data-stu-id="42c3e-246">To run the File Adapter sample</span></span>  

1. <span data-ttu-id="42c3e-247">单击**启动**，依次指向**所有程序**，指向**附件**，然后单击**Windows 资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-247">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Windows Explorer**.</span></span>  

2. <span data-ttu-id="42c3e-248">在 BizTalk Server 安装驱动器上创建以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="42c3e-248">Create the following folders on the BizTalk Server installation drive:</span></span>  

   -   <span data-ttu-id="42c3e-249">*\<drive\>*:**\Temp**</span><span class="sxs-lookup"><span data-stu-id="42c3e-249">*\<drive\>*:**\Temp**</span></span>  

   -   <span data-ttu-id="42c3e-250">*\<drive\>*:**\Temp\Send**</span><span class="sxs-lookup"><span data-stu-id="42c3e-250">*\<drive\>*:**\Temp\Send**</span></span>  

   -   <span data-ttu-id="42c3e-251">*\<drive\>*:**\Temp\Receive**</span><span class="sxs-lookup"><span data-stu-id="42c3e-251">*\<drive\>*:**\Temp\Receive**</span></span>  

3. <span data-ttu-id="42c3e-252">若要关闭 Windows 资源管理器，在**文件**菜单上，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-252">To close Windows Explorer, on the **File** menu, click **Close**.</span></span>  

4. <span data-ttu-id="42c3e-253">单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-253">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

5. <span data-ttu-id="42c3e-254">右键单击**BizTalk Server 管理**节点，然后选择**连接到现有组**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-254">Right-click the **BizTalk Server Administration**  node and select **Connect to Existing Group**.</span></span>  

6. <span data-ttu-id="42c3e-255">在中**连接到现有 BizTalk Server 配置数据库**对话框框中，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="42c3e-255">In the **Connect to Existing BizTalk Server Configuration Database** dialog box, do the following.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="42c3e-256">BizTalk 管理数据库也称为 BizTalk 配置数据库。</span><span class="sxs-lookup"><span data-stu-id="42c3e-256">The BizTalk Management database is also referred to as the BizTalk Configuration database.</span></span>  

   |    <span data-ttu-id="42c3e-257">使用此选项</span><span class="sxs-lookup"><span data-stu-id="42c3e-257">Use this</span></span>    |                                                                                    <span data-ttu-id="42c3e-258">执行的操作</span><span class="sxs-lookup"><span data-stu-id="42c3e-258">To do this</span></span>                                                                                     |
   |----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="42c3e-259">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="42c3e-259">**SQL Server**</span></span> |                                                                              <span data-ttu-id="42c3e-260">类型 **。**</span><span class="sxs-lookup"><span data-stu-id="42c3e-260">Type **.**</span></span> <span data-ttu-id="42c3e-261">（句点）。</span><span class="sxs-lookup"><span data-stu-id="42c3e-261">(a period).</span></span>                                                                               |
   |  <span data-ttu-id="42c3e-262">**“数据库”**</span><span class="sxs-lookup"><span data-stu-id="42c3e-262">**Database**</span></span>  | <span data-ttu-id="42c3e-263">选择配置向导创建的 BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="42c3e-263">Select the name of the BizTalk Management database that was created by the Configuration Wizard.</span></span> <span data-ttu-id="42c3e-264">使用配置向导的默认数据库名称是**BizTalkMgmtDb**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-264">The default database name used by the Configuration Wizard is **BizTalkMgmtDb**.</span></span> |


7. <span data-ttu-id="42c3e-265">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="42c3e-265">Click **OK**.</span></span>  

8. <span data-ttu-id="42c3e-266">展开**BizTalk 组 [*服务器名称*]** 中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**应用程序**节点，展开**BizTalk Application 1**节点。</span><span class="sxs-lookup"><span data-stu-id="42c3e-266">Expand the **BizTalk Group[*server name*]** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand the **Applications** node, expand the  **BizTalk Application 1** node.</span></span>  

9. <span data-ttu-id="42c3e-267">右键单击**发送端口**节点，并单击**新建**，选择**静态单向发送端口**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-267">Right-click the **Send Ports** node, and then click **New**, select **Static One-Way Send Port**, and then click **OK**.</span></span>  

10. <span data-ttu-id="42c3e-268">在中**发送端口属性**对话框中，选择**常规**，并执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="42c3e-268">In the **Send Port Properties** dialog box, select **General**, and do the following.</span></span>  


    |      <span data-ttu-id="42c3e-269">使用此选项</span><span class="sxs-lookup"><span data-stu-id="42c3e-269">Use this</span></span>      |                                                                                                                                                                                   <span data-ttu-id="42c3e-270">执行的操作</span><span class="sxs-lookup"><span data-stu-id="42c3e-270">To do this</span></span>                                                                                                                                                                                   |
    |--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    |      <span data-ttu-id="42c3e-271">**名称**</span><span class="sxs-lookup"><span data-stu-id="42c3e-271">**Name**</span></span>      |                                                                                                                                                                             <span data-ttu-id="42c3e-272">类型**AdapterSend**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-272">Type **AdapterSend**.</span></span>                                                                                                                                                                              |
    | <span data-ttu-id="42c3e-273">**传输类型**</span><span class="sxs-lookup"><span data-stu-id="42c3e-273">**Transport Type**</span></span> | <span data-ttu-id="42c3e-274">选择**静态**从下拉列表单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-274">Select **Static** from the drop-down list and click **Configure**.</span></span><br /><br /> <span data-ttu-id="42c3e-275">-在**Directory**框中，键入 \***\<驱动器\>\*:\Temp\Send**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-275">-   In the **Directory** box, type \***\<drive\>\*:\Temp\Send**.</span></span><br /><span data-ttu-id="42c3e-276">-在**文件模式**框中，选择**CreateNew**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-276">-   In the **File Mode** box, select **CreateNew**.</span></span><br /><span data-ttu-id="42c3e-277">-在**文件名**框中，键入 **%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-277">-   In the **File Name** box, type **%MessageID%.xml**.</span></span><br /><span data-ttu-id="42c3e-278">-单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-278">-   Click **OK**.</span></span><br /><span data-ttu-id="42c3e-279">- **URI**字段应该显示 \***\<驱动器\>\*:\Temp\Send\\%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-279">-   The **URI** field should show \***\<drive\>\*:\Temp\Send\\%MessageID%.xml**.</span></span> |
    | <span data-ttu-id="42c3e-280">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="42c3e-280">**Send pipeline**</span></span>  |                                                                                                                                   <span data-ttu-id="42c3e-281">选择**PassThruTransmit (Microsoft.BizTalk.DefaultPipelines.PassThruTransmit)**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-281">Select **PassThruTransmit (Microsoft.BizTalk.DefaultPipelines.PassThruTransmit)**, and then click **OK**.</span></span>                                                                                                                                    |


11. <span data-ttu-id="42c3e-282">下**BizTalk Application 1**节点单击**接收端口**，然后选择**新建 / 单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-282">Under the **BizTalk Application 1** node click **Receive Ports**, and select **New / One-Way Receive Port**.</span></span>  

12. <span data-ttu-id="42c3e-283">中**创建新接收端口**对话框中，在**指定的接收端口类型**框中，选择**单向接收端口**从下拉列表，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-283">In the **Create New Receive Port** dialog box, in the **Specify the type of Receive Port** box, select **One-way Receive Port** from the drop-down list, and then click **OK**.</span></span>  

13. <span data-ttu-id="42c3e-284">在中**接收端口属性**对话框中**名称**框中，键入**AdapterReceive**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-284">In the **Receive Port Properties** dialog box, in the **Name** box, type **AdapterReceive**, and then click **OK**.</span></span>  

14. <span data-ttu-id="42c3e-285">下**BizTalk Application 1**右键单击节点**接收位置**，然后选择**新建 / 单向接收位置**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-285">Under the **BizTalk Application 1** node right click **Receive Locations**, and select **New / One-way Receive Location**.</span></span>  

15. <span data-ttu-id="42c3e-286">在中**选择接收端口**对话框中，选择**AdapterReceive**然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-286">In the **Select a Receive Port** dialog, select **AdapterReceive** then click **OK**.</span></span>  

16. <span data-ttu-id="42c3e-287">在中**接收位置属性**对话框框中，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="42c3e-287">In the **Receive Location Properties** dialog box, do the following.</span></span>  


    |       <span data-ttu-id="42c3e-288">使用此选项</span><span class="sxs-lookup"><span data-stu-id="42c3e-288">Use this</span></span>       |                                                                                                                                                                                               <span data-ttu-id="42c3e-289">执行的操作</span><span class="sxs-lookup"><span data-stu-id="42c3e-289">To do this</span></span>                                                                                                                                                                                                |
    |----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    |       <span data-ttu-id="42c3e-290">**名称**</span><span class="sxs-lookup"><span data-stu-id="42c3e-290">**Name**</span></span>       |                                                                                                                                                                                     <span data-ttu-id="42c3e-291">类型**AdapterReceiveLocation**</span><span class="sxs-lookup"><span data-stu-id="42c3e-291">Type **AdapterReceiveLocation**</span></span>                                                                                                                                                                                     |
    |  <span data-ttu-id="42c3e-292">**传输类型**</span><span class="sxs-lookup"><span data-stu-id="42c3e-292">**Transport Type**</span></span>  |                                                                                                                                                  <span data-ttu-id="42c3e-293">选择**静态**从下拉列表和命中**配置**以访问其余属性。</span><span class="sxs-lookup"><span data-stu-id="42c3e-293">Select **Static** from the drop-down list and hit **Configure** to access these remaining properties.</span></span>                                                                                                                                                  |
    |       <span data-ttu-id="42c3e-294">**URI**</span><span class="sxs-lookup"><span data-stu-id="42c3e-294">**URI**</span></span>        | <span data-ttu-id="42c3e-295">-单击省略号按钮 (**...**).</span><span class="sxs-lookup"><span data-stu-id="42c3e-295">-   Click the ellipsis button (**…**).</span></span><br /><span data-ttu-id="42c3e-296">-在**数量的文件中批处理**框中，键入**20**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-296">-   In the **Number Of Files In Batch** box, type **20**.</span></span><br /><span data-ttu-id="42c3e-297">-在**Directory**框中，键入 \***\<驱动器\>\*:\Temp\Receive**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-297">-   In the **Directory** box, type \***\<drive\>\*:\Temp\Receive**.</span></span><br /><span data-ttu-id="42c3e-298">-确保**文件掩码**属性设置为 **\*.xml**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-298">-   Ensure the **File Mask** property is set to **\*.xml**.</span></span><br /><span data-ttu-id="42c3e-299">-在**轮询间隔**框中，键入**5**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-299">-   In the **Polling Interval** box, type **5**, and click **OK**.</span></span><br /><span data-ttu-id="42c3e-300">-确保**URI**标签包含 \***\<驱动器\>\*:\Temp\Receive\\\*.xml**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-300">-   Ensure the **URI** label contains \***\<drive\>\*:\Temp\Receive\\\*.xml**.</span></span> |
    | <span data-ttu-id="42c3e-301">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="42c3e-301">**Receive Handler**</span></span>  |                                                                                                                                                                      <span data-ttu-id="42c3e-302">选择**BizTalkServerApplication**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="42c3e-302">Select **BizTalkServerApplication** from the drop-down list.</span></span>                                                                                                                                                                       |
    | <span data-ttu-id="42c3e-303">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="42c3e-303">**Receive Pipeline**</span></span> |                                                                                                                                                                             <span data-ttu-id="42c3e-304">选择**XMLReceive**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="42c3e-304">Select **XMLReceive** from the drop-down list.</span></span>                                                                                                                                                                              |


17. <span data-ttu-id="42c3e-305">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="42c3e-305">Click **OK**.</span></span>  

     <span data-ttu-id="42c3e-306">请继续执行*构建、 部署和绑定示例适配器*。</span><span class="sxs-lookup"><span data-stu-id="42c3e-306">Proceed to *Building, Deploying, and Binding the Sample Adapter*.</span></span>  

### <a name="building-deploying-and-binding-the-sample-adapter"></a><span data-ttu-id="42c3e-307">生成、 部署和绑定示例适配器</span><span class="sxs-lookup"><span data-stu-id="42c3e-307">Building, Deploying, and Binding the Sample Adapter</span></span>  
 <span data-ttu-id="42c3e-308">在适配器投入使用前，必须生成项目、 绑定业务流程与端口并登记适配器。</span><span class="sxs-lookup"><span data-stu-id="42c3e-308">Before the adapter goes live, you must build the project, bind the orchestration with the ports, and enlist the adapter.</span></span>  

##### <a name="to-create-a-strong-name-key-for-the-static-adapter"></a><span data-ttu-id="42c3e-309">若要创建静态适配器的强名称密钥</span><span class="sxs-lookup"><span data-stu-id="42c3e-309">To create a strong name key for the static adapter</span></span>  

1.  <span data-ttu-id="42c3e-310">启动**Visual Studio 命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-310">Start **Visual Studio Command Prompt**.</span></span>  

2.  <span data-ttu-id="42c3e-311">在命令提示符下，将当前目录更改为\<*示例路径*\>**\AdaptersDevelopment\File Adapter\BizTalk Project\Adapter 工具**目录。</span><span class="sxs-lookup"><span data-stu-id="42c3e-311">At the command prompt, change the current directory to the \<*Samples Path*\>**\AdaptersDevelopment\File Adapter\BizTalk Project\Adapter Harness** directory.</span></span>  

3.  <span data-ttu-id="42c3e-312">在命令提示符处，键入**sn – k AdapterHarness.snk**，然后按 enter。</span><span class="sxs-lookup"><span data-stu-id="42c3e-312">At the command prompt, type **sn –k AdapterHarness.snk**, and then pressENTER.</span></span>  

4.  <span data-ttu-id="42c3e-313">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="42c3e-313">Click **OK**.</span></span>  

##### <a name="to-build-the-adapter-harness-project"></a><span data-ttu-id="42c3e-314">若要生成适配器管理项目</span><span class="sxs-lookup"><span data-stu-id="42c3e-314">To build the Adapter Harness project</span></span>  

-   <span data-ttu-id="42c3e-315">在解决方案资源管理器中右键单击**AdapterHarnessProject**，然后单击**重新生成**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-315">In Solution Explorer, right-click **AdapterHarnessProject**, and then click **Rebuild**.</span></span>  

##### <a name="to-deploy-the-adapter-harness-project"></a><span data-ttu-id="42c3e-316">若要部署适配器管理项目</span><span class="sxs-lookup"><span data-stu-id="42c3e-316">To deploy the Adapter Harness project</span></span>  

1.  <span data-ttu-id="42c3e-317">在解决方案资源管理器，该项目已重新生成时，右键单击**AdapterHarnessProject**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-317">In Solution Explorer, when the project has rebuilt, right-click **AdapterHarnessProject**, and then click **Deploy**.</span></span>  

2.  <span data-ttu-id="42c3e-318">在 BizTalk Server 管理控制台中，选择的项目已部署，然后依次**刷新**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-318">In BizTalk Server Administration console, select the project you have deployed, and then click **Refresh**.</span></span>  

##### <a name="to-bind-the-orchestration-with-the-ports"></a><span data-ttu-id="42c3e-319">若要将端口与业务流程绑定</span><span class="sxs-lookup"><span data-stu-id="42c3e-319">To bind the orchestration with the ports</span></span>  

1. <span data-ttu-id="42c3e-320">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中的，在相应[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序中，展开**业务流程**节点。</span><span class="sxs-lookup"><span data-stu-id="42c3e-320">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, under the appropriate [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application, expand the **Orchestrations** node.</span></span>  

2. <span data-ttu-id="42c3e-321">右键单击**AdapterHarness.AdapterHarnessType**，然后单击**绑定**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-321">Right-click **AdapterHarness.AdapterHarnessType**, and then click **Bind**.</span></span>  

3. <span data-ttu-id="42c3e-322">在中**端口绑定属性-AdapterHarness.AdapterHarnessType-绑定配置**对话框框中，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="42c3e-322">In the **Port Binding Properties - AdapterHarness.AdapterHarnessType- Binding Configurations** dialog box, do the following.</span></span>  


   |          <span data-ttu-id="42c3e-323">使用此选项</span><span class="sxs-lookup"><span data-stu-id="42c3e-323">Use this</span></span>          |                     <span data-ttu-id="42c3e-324">执行的操作</span><span class="sxs-lookup"><span data-stu-id="42c3e-324">To do this</span></span>                     |
   |----------------------------|----------------------------------------------------|
   | <span data-ttu-id="42c3e-325">**AdapterFileReceivePort**</span><span class="sxs-lookup"><span data-stu-id="42c3e-325">**AdapterFileReceivePort**</span></span> | <span data-ttu-id="42c3e-326">选择**AdapterReceive**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="42c3e-326">Select **AdapterReceive** from the drop-down list.</span></span> |
   |  <span data-ttu-id="42c3e-327">**AdapterFileSendPort**</span><span class="sxs-lookup"><span data-stu-id="42c3e-327">**AdapterFileSendPort**</span></span>   |  <span data-ttu-id="42c3e-328">选择**AdapterSend**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="42c3e-328">Select **AdapterSend** from the drop-down list.</span></span>   |


4. <span data-ttu-id="42c3e-329">在左窗格中，单击**主机**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-329">In the left pane, click **Host**.</span></span>  

5. <span data-ttu-id="42c3e-330">在中**主机**框中，选择**BizTalkServerApplication**从下拉列表中，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-330">In the **Host** box, select **BizTalkServerApplication** from the drop-down list, and then click **OK**.</span></span>  

   <span data-ttu-id="42c3e-331">请继续执行*管理示例适配器*。</span><span class="sxs-lookup"><span data-stu-id="42c3e-331">Proceed to *Administering the Sample Adapter*.</span></span>  

### <a name="administering-the-sample-adapter"></a><span data-ttu-id="42c3e-332">管理示例适配器</span><span class="sxs-lookup"><span data-stu-id="42c3e-332">Administering the Sample Adapter</span></span>  
 <span data-ttu-id="42c3e-333">完成示例适配器在 BizTalk 管理控制台中的管理任务。</span><span class="sxs-lookup"><span data-stu-id="42c3e-333">You complete administration tasks for the sample adapter in the BizTalk Administration console.</span></span>  

##### <a name="to-administer-the-file-adapter-sample"></a><span data-ttu-id="42c3e-334">若要管理文件适配器示例</span><span class="sxs-lookup"><span data-stu-id="42c3e-334">To administer the File Adapter sample</span></span>  

1. <span data-ttu-id="42c3e-335">单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-335">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="42c3e-336">在左窗格中，依次单击展开**应用程序**，单击此项可展开**BizTalk Application 1**，然后单击**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-336">In the left pane, click to expand **Applications**, click to expand **BizTalk Application 1**, and click **Receive Locations**.</span></span>  

3. <span data-ttu-id="42c3e-337">请确保**AdapterReceive**状态**已启用**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-337">Ensure the **AdapterReceive** status is **Enabled**.</span></span>  

    <span data-ttu-id="42c3e-338">如果状态不是**已启用**，右键单击**AdapterReceive**在右窗格中，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-338">If the status is not **Enabled**, right-click **AdapterReceive** in the right pane, and then click **Enable**.</span></span>  

4. <span data-ttu-id="42c3e-339">在左窗格中，单击**业务流程**并确保**AdapterHarness.AdapterHarnessType**是**已登记**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-339">In the left pane, click **Orchestrations** and ensure that **AdapterHarness.AdapterHarnessType** is **Enlisted**.</span></span> <span data-ttu-id="42c3e-340">右键单击**AdapterHarness.AdapterHarnessType**，然后单击**登记**(如果 AdapterHarness.AdapterHarnessType 已经登记，**登记**菜单选项不可用）。</span><span class="sxs-lookup"><span data-stu-id="42c3e-340">Right click **AdapterHarness.AdapterHarnessType**, and then click **Enlist** (if AdapterHarness.AdapterHarnessType is already enlisted, the **Enlist** menu option is unavailable).</span></span>  

5. <span data-ttu-id="42c3e-341">右键单击**AdapterHarness.AdapterHarnessType** ，然后选择**启动**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-341">Right-click **AdapterHarness.AdapterHarnessType** and select **Start**.</span></span> <span data-ttu-id="42c3e-342">此业务流程的状态应更改为**运行**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-342">The status of this orchestration should change to **Running**.</span></span>  

   <span data-ttu-id="42c3e-343">请继续执行*测试示例适配器*。</span><span class="sxs-lookup"><span data-stu-id="42c3e-343">Proceed to *Testing the Sample Adapter*.</span></span>  

### <a name="testing-the-sample-adapter"></a><span data-ttu-id="42c3e-344">测试示例适配器</span><span class="sxs-lookup"><span data-stu-id="42c3e-344">Testing the Sample Adapter</span></span>  
 <span data-ttu-id="42c3e-345">部署示例适配器后，必须停止并重新启动主机实例。</span><span class="sxs-lookup"><span data-stu-id="42c3e-345">After you deploy the sample adapter, you must stop and restart the host instance.</span></span> <span data-ttu-id="42c3e-346">将其放入生产之前测试示例适配器至关重要。</span><span class="sxs-lookup"><span data-stu-id="42c3e-346">It is critical that you test the sample adapter before you place it into production.</span></span>  

##### <a name="to-stop-and-restart-the-host-instance"></a><span data-ttu-id="42c3e-347">若要停止并重新启动主机实例</span><span class="sxs-lookup"><span data-stu-id="42c3e-347">To stop and restart the host instance</span></span>  

1.  <span data-ttu-id="42c3e-348">在中**BizTalk Server 管理**控制台中，单击以展开**BizTalk Server 管理**，单击此项可展开**BizTalk 组**，单击此项可展开**平台设置**然后单击**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-348">In the **BizTalk Server Administration** console, click to expand **BizTalk Server Administration**, click to expand **BizTalk Group**, click to expand **Platform Settings** and click **Host Instances**.</span></span> <span data-ttu-id="42c3e-349">在右窗格中选择 BizTalkServerApplication。</span><span class="sxs-lookup"><span data-stu-id="42c3e-349">Select the BizTalkServerApplication in the right pane.</span></span>  

2.  <span data-ttu-id="42c3e-350">右键单击主机实例 （通常情况下，计算机名称），然后依次**停止**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-350">Right-click the host instance (typically, the computer name), and then click **Stop**.</span></span>  

     <span data-ttu-id="42c3e-351">主机实例的状态将变为**已停止**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-351">The status of the host instance changes to **Stopped**.</span></span>  

3.  <span data-ttu-id="42c3e-352">右键单击该主机实例，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-352">Right-click the host instance, and then click **Start**.</span></span>  

     <span data-ttu-id="42c3e-353">主机实例的状态将变为**运行**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-353">The status of the host instance changes to **Running**.</span></span>  

##### <a name="to-test-the-sample-static-adapter-runtime"></a><span data-ttu-id="42c3e-354">若要测试示例静态适配器运行时</span><span class="sxs-lookup"><span data-stu-id="42c3e-354">To test the sample static adapter runtime</span></span>  

1.  <span data-ttu-id="42c3e-355">在 Windows 资源管理器，导航到\<*示例路径*\>**\AdaptersDevelopment\File 适配器**目录，并复制到剪贴板 InstanceXML.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="42c3e-355">In Windows Explorer, navigate to the \<*Samples Path*\>**\AdaptersDevelopment\File Adapter** directory, and copy the InstanceXML.xml file to your clipboard.</span></span>  

2.  <span data-ttu-id="42c3e-356">导航到*\<驱动器\>*:**\Temp\Receive** Instance.xml 文件并粘贴到该文件夹。</span><span class="sxs-lookup"><span data-stu-id="42c3e-356">Navigate to *\<drive\>*:**\Temp\Receive** and paste the Instance.xml file into the folder.</span></span>  

     <span data-ttu-id="42c3e-357">如果传输和接收适配器正在工作，该文件应移*\<驱动器\>*:**\Temp\Receive**文件夹*\<驱动器\>* :**\Temp\Send**文件夹。</span><span class="sxs-lookup"><span data-stu-id="42c3e-357">If the transmit and receive adapters are working, the file should move from the *\<drive\>*:**\Temp\Receive** folder to the *\<drive\>*:**\Temp\Send** folder.</span></span>  

##### <a name="to-test-the-sample-add-adapter-wizard-functionality-for-the-sample-static-adapter"></a><span data-ttu-id="42c3e-358">若要测试示例静态适配器的示例添加适配器向导功能</span><span class="sxs-lookup"><span data-stu-id="42c3e-358">To test the sample Add Adapter Wizard functionality for the sample static adapter</span></span>  

1. <span data-ttu-id="42c3e-359">在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器中右键单击**AdapterHarnessProject**，依次指向**添加**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-359">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], in Solution Explorer, right-click **AdapterHarnessProject**, point to **Add**, and then click **Add Generated Items**.</span></span>  

2. <span data-ttu-id="42c3e-360">在中**添加生成的项目-AdapterHarnessProject**对话框中，单击**添加适配器元数据**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-360">In the **Add Generated Items - AdapterHarnessProject** dialog box, click **Add Adapter Metadata**, and then click **Open**.</span></span>  

    <span data-ttu-id="42c3e-361">将显示已注册适配器列表。</span><span class="sxs-lookup"><span data-stu-id="42c3e-361">The list of registered adapters appears.</span></span>  

3. <span data-ttu-id="42c3e-362">选择**Static DotNetFile**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-362">Select **Static DotNetFile**, and then click **Next**.</span></span>  

    <span data-ttu-id="42c3e-363">将显示由适配器公开的服务组织。</span><span class="sxs-lookup"><span data-stu-id="42c3e-363">The service organization exposed by the adapter appears.</span></span>  

4. <span data-ttu-id="42c3e-364">展开**服务组织**，**卫生保健**，然后单击**管理**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-364">Expand **Service Organization**, **Health Care**, and then click **Administrative**.</span></span>  

    <span data-ttu-id="42c3e-365">请注意，**资格**以不同方式显示来自其他节点。</span><span class="sxs-lookup"><span data-stu-id="42c3e-365">Notice that **Eligibility** displays differently from the other nodes.</span></span> <span data-ttu-id="42c3e-366">**资格**是可以选择一个服务节点。</span><span class="sxs-lookup"><span data-stu-id="42c3e-366">**Eligibility** is a service node that you can select.</span></span> <span data-ttu-id="42c3e-367">其他节点是不会介绍任何特定服务的组织节点。</span><span class="sxs-lookup"><span data-stu-id="42c3e-367">The other nodes are organization nodes that do not describe any specific service.</span></span>  

5. <span data-ttu-id="42c3e-368">选择**资格**节点，并单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="42c3e-368">Select the **Eligibility** node, and then click **Finish**.</span></span>  

    <span data-ttu-id="42c3e-369">BizTalk 将.odx 文件和一个.xsd 文件导入项目。</span><span class="sxs-lookup"><span data-stu-id="42c3e-369">BizTalk imports an .odx file and an .xsd file into the project.</span></span>  

    <span data-ttu-id="42c3e-370">现在可以使用架构、 Porttype、 操作和 Messagetype 从适配器的 BizTalk 项目计划中导入。</span><span class="sxs-lookup"><span data-stu-id="42c3e-370">You can now use the schemas, PortTypes, Operations, and MessageTypes imported from the adapter in the schedule for the BizTalk project.</span></span>  

## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="42c3e-371">类或方法在此示例中使用</span><span class="sxs-lookup"><span data-stu-id="42c3e-371">Classes or Methods used in this Sample</span></span>  
 <span data-ttu-id="42c3e-372">接口：IBaseMessage、 IPropertyBag、 IBTTransportProxy</span><span class="sxs-lookup"><span data-stu-id="42c3e-372">Interfaces: IBaseMessage, IPropertyBag, IBTTransportProxy</span></span>  

 <span data-ttu-id="42c3e-373">类 （来自基本适配器）：AsyncTransmitterEndpoint, AsyncTransmitter, BatchMessage, ControlledTermination, ReceiverEndpoint, DotNetFileCommonProperties, BatchOperationType</span><span class="sxs-lookup"><span data-stu-id="42c3e-373">Classes (from Base Adapter): AsyncTransmitterEndpoint, AsyncTransmitter, BatchMessage, ControlledTermination, ReceiverEndpoint, DotNetFileCommonProperties, BatchOperationType</span></span>  

### <a name="comments"></a><span data-ttu-id="42c3e-374">注释</span><span class="sxs-lookup"><span data-stu-id="42c3e-374">Comments</span></span>  
 <span data-ttu-id="42c3e-375">示例适配器后，可以修改示例适配器创建自定义的静态或动态适配器的详细信息，请参阅[适配器设计时配置](../core/adapter-design-time-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="42c3e-375">After completing the sample adapter, you can modify the sample adapter to create a custom static or dynamic adapter For more information, see [Adapter Design-Time Configuration](../core/adapter-design-time-configuration.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="42c3e-376">请参阅</span><span class="sxs-lookup"><span data-stu-id="42c3e-376">See Also</span></span>  
 <span data-ttu-id="42c3e-377">[适配器示例-用法](../core/adapter-samples-usage.md) </span><span class="sxs-lookup"><span data-stu-id="42c3e-377">[Adapter Samples - Usage](../core/adapter-samples-usage.md) </span></span>  
 [<span data-ttu-id="42c3e-378">注册适配器</span><span class="sxs-lookup"><span data-stu-id="42c3e-378">Registering an Adapter</span></span>](../core/registering-an-adapter.md)