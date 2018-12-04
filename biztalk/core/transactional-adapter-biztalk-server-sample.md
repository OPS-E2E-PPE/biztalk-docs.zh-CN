---
title: 事务性适配器 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31a13377-cc89-4763-ad1b-508a16fc9708
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07719f864f332d644d201e6f8349bdc19b456a9f
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2018
ms.locfileid: "52826405"
---
# <a name="transactional-adapter-biztalk-server-sample"></a><span data-ttu-id="3fa47-102">事务性适配器 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="3fa47-102">Transactional Adapter (BizTalk Server Sample)</span></span>
<span data-ttu-id="3fa47-103">事务性适配器示例演示如何在处理 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 消息期间，根据数据库创建并使用显式 Microsoft 分布式事务处理协调器 (MSDTC) 事务。</span><span class="sxs-lookup"><span data-stu-id="3fa47-103">The Transactional Adapter sample demonstrates how to create and use an explicit Microsoft Distributed Transaction Coordinator (MSDTC) transaction against a database during processing of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] message.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="3fa47-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="3fa47-104">What This Sample Does</span></span>  
 <span data-ttu-id="3fa47-105">此示例包含一个接收适配器，该适配器以用户指定的间隔运行 SQL 语句，使用 MSDTC 事务从 SQL Server 数据库中获取数据。</span><span class="sxs-lookup"><span data-stu-id="3fa47-105">This sample contains a receive adapter which runs a SQL statement at a user-specified interval to obtain data from a SQL Server database using an MSDTC transaction.</span></span> <span data-ttu-id="3fa47-106">然后，以同一事务上下文中的消息的形式将数据提交给 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="3fa47-106">The data is then submitted to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MessageBox database in the form of a message under the context of the same transaction.</span></span>  

 <span data-ttu-id="3fa47-107">相应的发送适配器使用来自事务上下文中 BizTalk 消息的输入运行用户指定的 SQL 存储过程。</span><span class="sxs-lookup"><span data-stu-id="3fa47-107">The corresponding send adapter runs a user-specified SQL stored procedure using input from a BizTalk message in the context of a transaction.</span></span> <span data-ttu-id="3fa47-108">它使用来自该消息中的特定数据，找到并删除同一事务中 MessageBox 数据库中对应的消息。</span><span class="sxs-lookup"><span data-stu-id="3fa47-108">It uses specific data from that message to locate and delete the corresponding message from the Message Box database under that same transaction.</span></span>  

## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="3fa47-109">此示例设计方式和原因</span><span class="sxs-lookup"><span data-stu-id="3fa47-109">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="3fa47-110">此示例在其解决方案中有两个项目。</span><span class="sxs-lookup"><span data-stu-id="3fa47-110">This sample has two projects in its solution.</span></span> <span data-ttu-id="3fa47-111">第一个是在运行前使用的管理项目 (Admin)，以允许用户配置使用此适配器的接收位置和发送端口。</span><span class="sxs-lookup"><span data-stu-id="3fa47-111">The first is the administrative project (Admin) which is used prior to runtime to allow a user to configure the receive locations and send ports that use this adapter.</span></span> <span data-ttu-id="3fa47-112">第二个是在发送和接收适配器正在执行时运行的运行时项目 (Runtime)。</span><span class="sxs-lookup"><span data-stu-id="3fa47-112">The second is the runtime project (Runtime) that runs when the send and receive adapters are executing.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="3fa47-113">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="3fa47-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="3fa47-114">本示例位于以下 SDK 位置中：</span><span class="sxs-lookup"><span data-stu-id="3fa47-114">The sample is located in the following SDK location:</span></span>  

 <span data-ttu-id="3fa47-115">\<*示例路径*\>\Samples\AdaptersDevelopment\TransactionalAdapter。</span><span class="sxs-lookup"><span data-stu-id="3fa47-115">\<*Samples Path*\>\Samples\AdaptersDevelopment\TransactionalAdapter.</span></span> <span data-ttu-id="3fa47-116">管理配置项目位于 \Admin 文件夹中，而运行时项目位于 \Runtime 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="3fa47-116">The administrative configuration project is located in the \Admin folder, while the runtime project exists in the \Runtime folder.</span></span>  

 <span data-ttu-id="3fa47-117">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="3fa47-117">The following table shows the files in this sample and describes their purpose.</span></span>  

|<span data-ttu-id="3fa47-118">Admin 项目文件名</span><span class="sxs-lookup"><span data-stu-id="3fa47-118">Admin Project Filename</span></span>|<span data-ttu-id="3fa47-119">Admin 项目文件说明</span><span class="sxs-lookup"><span data-stu-id="3fa47-119">Admin Project File Description</span></span>|  
|----------------------------|------------------------------------|  
|<span data-ttu-id="3fa47-120">TransactionalAdmin.csproj</span><span class="sxs-lookup"><span data-stu-id="3fa47-120">TransactionalAdmin.csproj</span></span>|<span data-ttu-id="3fa47-121">用于进行运行时预配置的适配器管理项目文件</span><span class="sxs-lookup"><span data-stu-id="3fa47-121">Adapter administrative project file used for pre-runtime configuration</span></span>|  
|<span data-ttu-id="3fa47-122">TransactionalReceiveHandler.xsd</span><span class="sxs-lookup"><span data-stu-id="3fa47-122">TransactionalReceiveHandler.xsd</span></span>|<span data-ttu-id="3fa47-123">接收处理程序属性的 XSD</span><span class="sxs-lookup"><span data-stu-id="3fa47-123">XSD for receive handler properties</span></span>|  
|<span data-ttu-id="3fa47-124">TransactionalReceiveLocation.xsd</span><span class="sxs-lookup"><span data-stu-id="3fa47-124">TransactionalReceiveLocation.xsd</span></span>|<span data-ttu-id="3fa47-125">接收位置属性的 XSD</span><span class="sxs-lookup"><span data-stu-id="3fa47-125">XSD for receive location properties</span></span>|  
|<span data-ttu-id="3fa47-126">TransactionalTransmitLocation.xsd</span><span class="sxs-lookup"><span data-stu-id="3fa47-126">TransactionalTransmitLocation.xsd</span></span>|<span data-ttu-id="3fa47-127">传输位置属性的 XSD</span><span class="sxs-lookup"><span data-stu-id="3fa47-127">XSD for transmit location properties</span></span>|  
|<span data-ttu-id="3fa47-128">TransactionalTransmitHandler.xsd</span><span class="sxs-lookup"><span data-stu-id="3fa47-128">TransactionalTransmitHandler.xsd</span></span>|<span data-ttu-id="3fa47-129">传输处理程序属性的 XSD</span><span class="sxs-lookup"><span data-stu-id="3fa47-129">XSD for transmit handler properties</span></span>|  
|<span data-ttu-id="3fa47-130">TransactionalAdapterManagement.cs</span><span class="sxs-lookup"><span data-stu-id="3fa47-130">TransactionalAdapterManagement.cs</span></span>|<span data-ttu-id="3fa47-131">适配器配置管理。</span><span class="sxs-lookup"><span data-stu-id="3fa47-131">Adapter configuration management.</span></span> <span data-ttu-id="3fa47-132">包含 GetConfigSchema，BizTalk 适配器框架调用 GetConfigSchema 以返回它所支持的每种（四种）可能配置类型的 XSD 配置架构。</span><span class="sxs-lookup"><span data-stu-id="3fa47-132">Contains GetConfigSchema which is invoked by the BizTalk Adapter Framework to return an XSD configuration schema for each of the (four) possible configuration types it supports.</span></span>|  

|<span data-ttu-id="3fa47-133">Runtime 项目文件名</span><span class="sxs-lookup"><span data-stu-id="3fa47-133">Runtime Project Filename</span></span>|<span data-ttu-id="3fa47-134">Runtime 项目文件说明</span><span class="sxs-lookup"><span data-stu-id="3fa47-134">Runtime Project File Description</span></span>|  
|------------------------------|--------------------------------------|  
|<span data-ttu-id="3fa47-135">Transactional.csproj</span><span class="sxs-lookup"><span data-stu-id="3fa47-135">Transactional.csproj</span></span>|<span data-ttu-id="3fa47-136">适配器运行时项目文件</span><span class="sxs-lookup"><span data-stu-id="3fa47-136">Adapter runtime project file</span></span>|  
|<span data-ttu-id="3fa47-137">TransactionalAsyncBatch.cs</span><span class="sxs-lookup"><span data-stu-id="3fa47-137">TransactionalAsyncBatch.cs</span></span>|<span data-ttu-id="3fa47-138">适配器发送部分的异步实现</span><span class="sxs-lookup"><span data-stu-id="3fa47-138">Asynchronous implementation of the send part of the adapter</span></span>|  
|<span data-ttu-id="3fa47-139">TransactionalDeleteBatch.cs</span><span class="sxs-lookup"><span data-stu-id="3fa47-139">TransactionalDeleteBatch.cs</span></span>|<span data-ttu-id="3fa47-140">删除一批消息和投票，以提交或中止事务</span><span class="sxs-lookup"><span data-stu-id="3fa47-140">Deletes a batch of messages and votes to commit or abort a transaction</span></span>|  
|<span data-ttu-id="3fa47-141">TransactionalProperties.cs</span><span class="sxs-lookup"><span data-stu-id="3fa47-141">TransactionalProperties.cs</span></span>|<span data-ttu-id="3fa47-142">提取和设置配置属性</span><span class="sxs-lookup"><span data-stu-id="3fa47-142">Extracts and sets configuration properties</span></span>|  
|<span data-ttu-id="3fa47-143">TransactionalReceiver.cs</span><span class="sxs-lookup"><span data-stu-id="3fa47-143">TransactionalReceiver.cs</span></span>|<span data-ttu-id="3fa47-144">创建和管理接收终结点</span><span class="sxs-lookup"><span data-stu-id="3fa47-144">Creates and manages receive endpoints</span></span>|  
|<span data-ttu-id="3fa47-145">TransactionalReceiverEndpoint.cs</span><span class="sxs-lookup"><span data-stu-id="3fa47-145">TransactionalReceiverEndpoint.cs</span></span>|<span data-ttu-id="3fa47-146">每个接收位置的实际监听或轮询</span><span class="sxs-lookup"><span data-stu-id="3fa47-146">Actual listening or polling for each receive location</span></span>|  
|<span data-ttu-id="3fa47-147">TransactionalTransmitter.cs</span><span class="sxs-lookup"><span data-stu-id="3fa47-147">TransactionalTransmitter.cs</span></span>|<span data-ttu-id="3fa47-148">从消息引擎接受要传输的一批消息</span><span class="sxs-lookup"><span data-stu-id="3fa47-148">Accepts a batch of messages from the Messaging Engine to be transmitted</span></span>|  

## <a name="how-to-use-this-sample"></a><span data-ttu-id="3fa47-149">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="3fa47-149">How to Use This Sample</span></span>  
 <span data-ttu-id="3fa47-150">本示例可以作为你使用显式事务创建自定义发送和接收适配器的框架。</span><span class="sxs-lookup"><span data-stu-id="3fa47-150">This sample is meant as a framework for you to use in creating custom send and receive adapters using explicit transactions.</span></span>  

## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="3fa47-151">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="3fa47-151">Building and Initializing This Sample</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="3fa47-152">如果是在 64 位计算机上安装 BizTalk 或安装位置已修改，则需要相应修改 OutboundAssemblyPath、InboundAssemblyPath、AdapterMgmtAssemblyPath。</span><span class="sxs-lookup"><span data-stu-id="3fa47-152">If the BizTalk installation is 64-bit or the location of installation is modified, OutboundAssemblyPath, InboundAssemblyPath, AdapterMgmtAssemblyPath would need to be changed accordingly.</span></span>  

#### <a name="create-a-strong-name-key-for-the-transactional-adapter-sample"></a><span data-ttu-id="3fa47-153">创建事务性适配器示例的强名称密钥</span><span class="sxs-lookup"><span data-stu-id="3fa47-153">Create a Strong Name Key for the Transactional Adapter sample</span></span>  

1.  <span data-ttu-id="3fa47-154">启动**Visual Studio 命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-154">Start **Visual Studio Command Prompt**.</span></span>  

2.  <span data-ttu-id="3fa47-155">在命令提示符下，键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="3fa47-155">At the command prompt, type the following and then press enter:</span></span>  

    ```  
    cd \Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersDevelopment\TransactionalAdapter\Runtime  
    ```  

3.  <span data-ttu-id="3fa47-156">在命令提示符下，键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="3fa47-156">At the command prompt, type the following and then press enter:</span></span>  

    ```  
    sn –k TransactionalAdapter.snk  
    ```  

4.  <span data-ttu-id="3fa47-157">在命令提示符处，键入**退出**，然后按 enter 以关闭命令提示符窗口。</span><span class="sxs-lookup"><span data-stu-id="3fa47-157">At the command prompt, type **exit**, and then press enter to close the command prompt window.</span></span>  

#### <a name="build-the-transactional-adapter-solution"></a><span data-ttu-id="3fa47-158">生成事务性适配器解决方案</span><span class="sxs-lookup"><span data-stu-id="3fa47-158">Build the Transactional Adapter Solution</span></span>  

1. <span data-ttu-id="3fa47-159">单击**启动**，依次指向**所有程序**，指向**附件**，然后单击**Windows 资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-159">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Windows Explorer**.</span></span>  

2. <span data-ttu-id="3fa47-160">浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AdaptersDevelopment\TransactionalAdapter，然后双击**TransactionalAdapter.sln**以打开此解决方案中的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3fa47-160">Browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AdaptersDevelopment\TransactionalAdapter, and double-click **TransactionalAdapter.sln** to open this solution in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  

3. <span data-ttu-id="3fa47-161">若要生成的两个事务性适配器项目 （Admin 和 Runtime） 在解决方案资源管理器中，右键单击**解决方案 TransactionalAdapter**，然后单击**重新生成**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-161">To build both of the Transactional Adapter projects (Admin and Runtime) in Solution Explorer, right-click **Solution TransactionalAdapter**, and then click **Rebuild**.</span></span>  

## <a name="running-this-sample"></a><span data-ttu-id="3fa47-162">运行本示例</span><span class="sxs-lookup"><span data-stu-id="3fa47-162">Running This Sample</span></span>  

#### <a name="register-the-transactional-adapter"></a><span data-ttu-id="3fa47-163">注册事务性适配器</span><span class="sxs-lookup"><span data-stu-id="3fa47-163">Register the Transactional Adapter</span></span>  

1. <span data-ttu-id="3fa47-164">在 Windows 资源管理器中，导航至 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AdaptersDevelopment\TransactionalAdapter\Admin。</span><span class="sxs-lookup"><span data-stu-id="3fa47-164">In Windows Explorer, navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AdaptersDevelopment\TransactionalAdapter\Admin.</span></span>  

2. <span data-ttu-id="3fa47-165">若要将事务性适配器数据添加到注册表中，双击**TransactionalAdmin.reg**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-165">To add the transactional adapter data to the registry, double-click **TransactionalAdmin.reg**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="3fa47-166">**TransactionalAdmin.reg**包括硬编码路径为 C:\Program Files\Microsoft BizTalk Server\\。</span><span class="sxs-lookup"><span data-stu-id="3fa47-166">**TransactionalAdmin.reg** includes hard-coded paths to C:\Program Files\Microsoft BizTalk Server\\.</span></span> <span data-ttu-id="3fa47-167">如果你的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的安装位置不是默认位置或者是从以前版本升级到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装，则必须使用相应的路径修改 TransactionalAdmin.reg 文件。</span><span class="sxs-lookup"><span data-stu-id="3fa47-167">If you did not install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the default location or if you upgraded your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation from a previous version, you must modify the file TransactionalAdmin.reg with the appropriate paths.</span></span> <span data-ttu-id="3fa47-168">更新与揑“InboundAssemblyPath”、揙“OutboundAssemblyPath”和揂“AdapterMgmtAssemblyPath”值相关联的路径，以指向指定文件的正确位置。</span><span class="sxs-lookup"><span data-stu-id="3fa47-168">Update the paths associated with the "InboundAssemblyPath", "OutboundAssemblyPath", and "AdapterMgmtAssemblyPath" values to point to the correct location of the specified files.</span></span>  
   > 
   > [!IMPORTANT]
   >  <span data-ttu-id="3fa47-169">如果在 64 位计算机上安装 BizTalk，将 HKEY_CLASSES_ROOT\CLSID\ 注册表项的所有实例都更改为 hkey_classes_root\wow6432node\clsid \ 中**TransactionalAdmin.reg**注册表文件。</span><span class="sxs-lookup"><span data-stu-id="3fa47-169">If you install BizTalk on a 64 bit machine, change all instances of the HKEY_CLASSES_ROOT\CLSID\ registry entry to HKEY_CLASSES_ROOT\Wow6432Node\CLSID\ in the **TransactionalAdmin.reg** registry file.</span></span>  

3. <span data-ttu-id="3fa47-170">在中**注册表编辑器**对话框中，单击**是**以将示例适配器添加到注册表，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-170">In the **Registry Editor** dialog box, click **Yes** to add the sample adapter to the registry, and then click **OK**.</span></span>  

4. <span data-ttu-id="3fa47-171">若要关闭 Windows 资源管理器中，单击**文件**，然后单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-171">To close Windows Explorer, click **File**, and then click **Close**.</span></span>  

#### <a name="add-the-transactional-adapter-to-biztalk-server"></a><span data-ttu-id="3fa47-172">将事务性适配器添加到 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="3fa47-172">Add the Transactional Adapter to BizTalk Server</span></span>  

1. <span data-ttu-id="3fa47-173">单击**启动**菜单中，选择**所有程序**，选择[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后选择**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-173">Click the **Start** menu, select **All Programs**, select [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then select **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="3fa47-174">在中[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk Server 管理**树中，展开**BizTalk 组**树、，然后展开**平台设置**树。</span><span class="sxs-lookup"><span data-stu-id="3fa47-174">In the [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the **BizTalk Server Administration** tree, expand the **BizTalk Group** tree, and then expand the **Platform Settings**  tree.</span></span>  

3. <span data-ttu-id="3fa47-175">右键单击**适配器**，单击**新建**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-175">Right-click **Adapters**, click **New**, and then click **Adapter**.</span></span>  

4. <span data-ttu-id="3fa47-176">在中**适配器属性**对话框框中，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="3fa47-176">In the **Adapter Properties** dialog box, do the following.</span></span>  


   |  <span data-ttu-id="3fa47-177">使用此选项</span><span class="sxs-lookup"><span data-stu-id="3fa47-177">Use this</span></span>   |                                                            <span data-ttu-id="3fa47-178">执行的操作</span><span class="sxs-lookup"><span data-stu-id="3fa47-178">To do this</span></span>                                                             |
   |-------------|-----------------------------------------------------------------------------------------------------------------------------------|
   |    <span data-ttu-id="3fa47-179">“属性”</span><span class="sxs-lookup"><span data-stu-id="3fa47-179">Name</span></span>     |                                                  <span data-ttu-id="3fa47-180">类型**TransactionalAdapter**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-180">Type **TransactionalAdapter**.</span></span>                                                   |
   |   <span data-ttu-id="3fa47-181">适配器</span><span class="sxs-lookup"><span data-stu-id="3fa47-181">Adapter</span></span>   | <span data-ttu-id="3fa47-182">选择**Txn**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="3fa47-182">Select **Txn** from the drop-down list.</span></span> <span data-ttu-id="3fa47-183">运行此项将出现**TransactionalAdmin.reg**以前文件。</span><span class="sxs-lookup"><span data-stu-id="3fa47-183">This entry appears as a result of running the **TransactionalAdmin.reg** file previously.</span></span> |
   | <span data-ttu-id="3fa47-184">Description</span><span class="sxs-lookup"><span data-stu-id="3fa47-184">Description</span></span> |                                              <span data-ttu-id="3fa47-185">类型**示例事务性适配器**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-185">Type **Sample Transactional Adapter**.</span></span>                                               |


5. <span data-ttu-id="3fa47-186">单击“确定” **。**</span><span class="sxs-lookup"><span data-stu-id="3fa47-186">Click **OK.**</span></span> <span data-ttu-id="3fa47-187">现在该适配器显示在 BizTalk 管理控制台右侧窗口中的适配器列表中。</span><span class="sxs-lookup"><span data-stu-id="3fa47-187">The adapter now appears in the list of adapters in the right window of the BizTalk Administration console.</span></span>  

#### <a name="create-a-receive-port-and-location-that-uses-the-adapter"></a><span data-ttu-id="3fa47-188">创建使用该适配器的接收端口和位置</span><span class="sxs-lookup"><span data-stu-id="3fa47-188">Create a Receive Port and Location that uses the Adapter</span></span>  

1. <span data-ttu-id="3fa47-189">展开**BizTalk 组 [服务器名称]** 中的节点[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**应用程序**节点，展开**BizTalk Application 1**节点。</span><span class="sxs-lookup"><span data-stu-id="3fa47-189">Expand the **BizTalk Group[server name]** node in [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **Applications** node, expand **BizTalk Application 1** node.</span></span>  

2. <span data-ttu-id="3fa47-190">右键单击**接收端口**，然后单击**新建**，选择**单向接收端口。**</span><span class="sxs-lookup"><span data-stu-id="3fa47-190">Right-click **Receive Ports**, and then click **New**, select **One-Way Receive Port.**</span></span>  

3. <span data-ttu-id="3fa47-191">有关**名称**，输入**TxnReceivePort1**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-191">For **Name**, enter **TxnReceivePort1**, and then click **OK**.</span></span>  

4. <span data-ttu-id="3fa47-192">右键单击**接收位置**节点中，单击**新建**，然后选择**单向接收位置**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-192">Right-click the **Receive Locations** node, click **New**, and then select **One-Way Receive Location**.</span></span>  

5. <span data-ttu-id="3fa47-193">在中**选择接收端口**对话框中，选择**TxnReceivePort1**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-193">In the**Select a Receive Port** dialog box, select **TxnReceivePort1**, and then click **OK**.</span></span>  

6. <span data-ttu-id="3fa47-194">在中**接收位置属性**对话框中的**常规**选项卡上，输入**TxnReceiveLocation1**有关**名称**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-194">In the **Receive Location Properties** dialog box, under the **General** tab, enter **TxnReceiveLocation1** for **Name**.</span></span> <span data-ttu-id="3fa47-195">请确保**接收端口**标签显示**TxnReceivePort1**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-195">Ensure the **Receive Port** label displays **TxnReceivePort1**.</span></span>  

7. <span data-ttu-id="3fa47-196">在中**类型**下拉列表框中**传输**框架中，选择**TransactionalAdapter。**</span><span class="sxs-lookup"><span data-stu-id="3fa47-196">In the**Type** dropdown list box, in the **Transport** frame, select **TransactionalAdapter.**</span></span>  

8. <span data-ttu-id="3fa47-197">在中**接收**<strong>管道</strong>框中，确保**PassThruReceive**处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="3fa47-197">In the **Receive**<strong>Pipeline</strong> box, ensure **PassThruReceive** is selected.</span></span> <span data-ttu-id="3fa47-198">将其他属性保留为默认设置。</span><span class="sxs-lookup"><span data-stu-id="3fa47-198">Leave the rest of the properties with their default settings.</span></span>  

9. <span data-ttu-id="3fa47-199">单击**配置**按钮旁边**类型**下拉框。</span><span class="sxs-lookup"><span data-stu-id="3fa47-199">Click the **Configure** button next to the **Type** drop down box.</span></span> <span data-ttu-id="3fa47-200">这会显示特定于此适配器的对话框。</span><span class="sxs-lookup"><span data-stu-id="3fa47-200">This displays a dialog specific to this adapter.</span></span> <span data-ttu-id="3fa47-201">指定以下内容，正如您看到合适，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-201">Specify the following as you see appropriate, then click **OK**.</span></span>  


   |       <span data-ttu-id="3fa47-202">“属性”</span><span class="sxs-lookup"><span data-stu-id="3fa47-202">Property</span></span>        |                                                                           <span data-ttu-id="3fa47-203">设置</span><span class="sxs-lookup"><span data-stu-id="3fa47-203">Setting</span></span>                                                                            |
   |-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   <span data-ttu-id="3fa47-204">连接字符串</span><span class="sxs-lookup"><span data-stu-id="3fa47-204">Connection String</span></span>   | <span data-ttu-id="3fa47-205">用于连接 Northwind 数据库并进行身份验证的 SQL 数据库连接字符串。</span><span class="sxs-lookup"><span data-stu-id="3fa47-205">The SQL database connection string used to connect and authenticate with the Northwind database.</span></span> <span data-ttu-id="3fa47-206">我们随后运行的 SQL 脚本将使用此数据库。</span><span class="sxs-lookup"><span data-stu-id="3fa47-206">We will later run a SQL script that will use this database.</span></span> |
   |     <span data-ttu-id="3fa47-207">命令文本</span><span class="sxs-lookup"><span data-stu-id="3fa47-207">Command Text</span></span>      |                      <span data-ttu-id="3fa47-208">针对 Northwind 数据库执行的 SQL 语句，目的是获取要输入到 BizTalk 消息中的数据。</span><span class="sxs-lookup"><span data-stu-id="3fa47-208">The SQL statements that are executed against the Northwind database to obtain data to put into a BizTalk Message.</span></span>                       |
   |        <span data-ttu-id="3fa47-209">Cookie</span><span class="sxs-lookup"><span data-stu-id="3fa47-209">Cookie</span></span>         |               <span data-ttu-id="3fa47-210">包括部分 URI，因此请输入唯一的值，如接收位置的名称，例如：TxnReceiveLocation1。</span><span class="sxs-lookup"><span data-stu-id="3fa47-210">Comprises part of the URI so enter a unique value, such as the name of the receive location, for instance: TxnReceiveLocation1.</span></span>                |
   | <span data-ttu-id="3fa47-211">轮询间隔单位</span><span class="sxs-lookup"><span data-stu-id="3fa47-211">Polling Interval Unit</span></span> |                                    <span data-ttu-id="3fa47-212">轮询数据的时间单位。</span><span class="sxs-lookup"><span data-stu-id="3fa47-212">The number of units of time measure for the polling of the data.</span></span> <span data-ttu-id="3fa47-213">设置为秒。</span><span class="sxs-lookup"><span data-stu-id="3fa47-213">Set this to seconds.</span></span>                                     |
   |   <span data-ttu-id="3fa47-214">轮询间隔</span><span class="sxs-lookup"><span data-stu-id="3fa47-214">Polling Interval</span></span>    |                                        <span data-ttu-id="3fa47-215">数据的轮询的时间度量单位。</span><span class="sxs-lookup"><span data-stu-id="3fa47-215">The unit of time measure for the polling of the data.</span></span> <span data-ttu-id="3fa47-216">设置为 15 秒。</span><span class="sxs-lookup"><span data-stu-id="3fa47-216">Set this to 15 seconds.</span></span>                                         |


10. <span data-ttu-id="3fa47-217">单击**确定**关闭配置对话框中，然后**确定**以关闭**接收位置属性**对话框中，以返回到[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3fa47-217">Click **OK** to close the Configure dialog box, then **OK** again to close the **Receive Location Properties** dialog box to return to the [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  

#### <a name="create-a-send-port-and-send-handler-that-use-the-adapter"></a><span data-ttu-id="3fa47-218">创建使用此适配器的发送端口和发送处理程序</span><span class="sxs-lookup"><span data-stu-id="3fa47-218">Create a Send Port and Send Handler that use the Adapter</span></span>  

1.  <span data-ttu-id="3fa47-219">与**BizTalk Application 1**节点处于展开状态中，右键单击**发送端口**，然后单击**新建**，然后选择**静态单向发送端口**.</span><span class="sxs-lookup"><span data-stu-id="3fa47-219">With the **BizTalk Application 1** node still expanded, right-click **Send Ports**, and then click **New**, and select **Static One-Way Send Port**.</span></span>  

2.  <span data-ttu-id="3fa47-220">在中**名称**字段中，输入**TxnSendPort1**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-220">In the **Name** field, enter **TxnSendPort1**.</span></span>  

3.  <span data-ttu-id="3fa47-221">在中**传输**帧，在**类型**下拉列表中，选择**TransactionalAdapter**`.`</span><span class="sxs-lookup"><span data-stu-id="3fa47-221">In the **Transport** frame, in the **Type** drop-down list, select**TransactionalAdapter**`.`</span></span>  

4.  <span data-ttu-id="3fa47-222">在中**发送管道**框中，确保**PassThruTransmit**处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="3fa47-222">In the **Send Pipeline** box, ensure **PassThruTransmit** is selected.</span></span>  

5.  <span data-ttu-id="3fa47-223">单击**配置**按钮旁边**传输**下拉列表。在出现的对话框中指定以下根据需要，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-223">Click the **Configure** button next to the **transport** drop-down list.In the dialog that appears specify the following as you see appropriate, then click **OK**.</span></span>  

    |<span data-ttu-id="3fa47-224">“属性”</span><span class="sxs-lookup"><span data-stu-id="3fa47-224">Property</span></span>|<span data-ttu-id="3fa47-225">设置</span><span class="sxs-lookup"><span data-stu-id="3fa47-225">Setting</span></span>|  
    |--------------|-------------|  
    |<span data-ttu-id="3fa47-226">Cookie</span><span class="sxs-lookup"><span data-stu-id="3fa47-226">Cookie</span></span>|<span data-ttu-id="3fa47-227">包括部分 uri-例如输入如接收位置的名称唯一此处的值： **TxnSendPort1**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-227">Comprises part of the URI - Enter a unique value here such as the name of the receive location, for instance: **TxnSendPort1**.</span></span>|  
    |<span data-ttu-id="3fa47-228">连接字符串</span><span class="sxs-lookup"><span data-stu-id="3fa47-228">Connection String</span></span>|<span data-ttu-id="3fa47-229">用于连接 Northwind 数据库并进行身份验证的 SQL 数据库连接字符串。</span><span class="sxs-lookup"><span data-stu-id="3fa47-229">The SQL database connection string used to connect and authenticate with the Northwind database.</span></span> <span data-ttu-id="3fa47-230">它很可能是用于配置的同一**TxnReceiveLocation1**接收位置。</span><span class="sxs-lookup"><span data-stu-id="3fa47-230">It will most likely be the same one used to configure the **TxnReceiveLocation1** receive location.</span></span>|  
    |<span data-ttu-id="3fa47-231">存储过程</span><span class="sxs-lookup"><span data-stu-id="3fa47-231">Stored Procedure</span></span>|<span data-ttu-id="3fa47-232">若要轮询数据库-获取执行的存储的过程名称**sp_txnProc**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-232">The stored procedure name that gets executed to poll the database - **sp_txnProc**.</span></span> <span data-ttu-id="3fa47-233">消息发送到的 BizTalk 正文作为字符串参数调用存储过程@Data。</span><span class="sxs-lookup"><span data-stu-id="3fa47-233">The body of the BizTalk message is given to that stored procedure as a string parameter called @Data.</span></span> <span data-ttu-id="3fa47-234">例如，用户将在这种情况下更高版本的存储的过程使用配置名称**sp_txnProc**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-234">For example, the user will in this case later configure the stored procedure with the name **sp_txnProc**.</span></span> <span data-ttu-id="3fa47-235">该适配器在运行时将对数据库执行等效的这种调用。</span><span class="sxs-lookup"><span data-stu-id="3fa47-235">The runtime of the adapter would execute the equivalent of this call to the database.</span></span><br /><br /> <span data-ttu-id="3fa47-236">exec sp_txnProc @Data ="BizTalk 消息的内容"</span><span class="sxs-lookup"><span data-stu-id="3fa47-236">exec sp_txnProc @Data = “the contents of the BizTalk message”</span></span>|  

6.  <span data-ttu-id="3fa47-237">在左侧的导航窗格中，单击**筛选器**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-237">In the left navigation pane, click **Filter**.</span></span>  

7.  <span data-ttu-id="3fa47-238">在筛选器表达式编辑器中，输入以下表达式以便设置针对此发送端口的订阅，接收由 TxnReceivePort1 接收端口接收到的任何消息。</span><span class="sxs-lookup"><span data-stu-id="3fa47-238">In the filter expression editor, enter the following expression to set up a subscription for this send port to receive any messages received by the TxnReceivePort1 receive port.</span></span>  

     <span data-ttu-id="3fa47-239">输入以下值：**BTS。ReceivePortName = = TxnReceivePort1**</span><span class="sxs-lookup"><span data-stu-id="3fa47-239">Enter these values:**BTS.ReceivePortName== TxnReceivePort1**</span></span>  

    1.  <span data-ttu-id="3fa47-240">`(property)`  **BTS。ReceivePortName**</span><span class="sxs-lookup"><span data-stu-id="3fa47-240">`(property)`  **BTS.ReceivePortName**</span></span>  

    2.  <span data-ttu-id="3fa47-241">`(operator)`  **==**</span><span class="sxs-lookup"><span data-stu-id="3fa47-241">`(operator)`  **==**</span></span>  

    3.  <span data-ttu-id="3fa47-242">`(value)`  **TxnReceivePort1**</span><span class="sxs-lookup"><span data-stu-id="3fa47-242">`(value)`  **TxnReceivePort1**</span></span>  

8.  <span data-ttu-id="3fa47-243">适配器属性的其余部分使用默认值，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-243">Use the default values for the remainder of the adapter properties and select **OK**.</span></span>  

## <a name="run-the-sample"></a><span data-ttu-id="3fa47-244">运行示例</span><span class="sxs-lookup"><span data-stu-id="3fa47-244">Run the sample</span></span>  

1. <span data-ttu-id="3fa47-245">单击**启动**，依次指向**所有程序**，指向**Microsoft SQL Server 2008 R2**，选择**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-245">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, select **SQL Server Management Studio**.</span></span>  

2. <span data-ttu-id="3fa47-246">在中**连接到服务器**对话框框中，请确保**服务器类型**设置为**数据库引擎**，并输入凭据进行身份验证到数据库服务器，然后选择**连接**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-246">In the **Connect to Server** dialog box, make sure **Server Type** is set to **Database Engine**, and enter credentials to authenticate to the database server, then select **Connect**.</span></span>  

3. <span data-ttu-id="3fa47-247">选择**新查询**工具栏按钮并粘贴到一个新的查询窗口，将测试表、 测试数据和测试以下存储过程到 Northwind 数据库。</span><span class="sxs-lookup"><span data-stu-id="3fa47-247">Select the **New Query** toolbar button and paste the following into the new query window to insert a test table, test data, and a test stored procedure into the Northwind database.</span></span> <span data-ttu-id="3fa47-248">选择**Execute**工具栏按钮。</span><span class="sxs-lookup"><span data-stu-id="3fa47-248">Select the **Execute** toolbar button.</span></span>  

   ```sql
   use [Northwind]  
   GO  
   if exists (select * from dbo.sysobjects where id = object_id(N'[dbo].[scratch]') and OBJECTPROPERTY(id, N'IsUserTable') = 1)  
   drop table [dbo].[scratch]  
   GO  
   CREATE TABLE [dbo].[scratch] (  
        [id] [int] IDENTITY (1, 1) NOT NULL ,  
        [msg] [nvarchar] (4000) NOT NULL   
   ) ON [PRIMARY]  
   GO  
   GRANT SELECT , UPDATE , INSERT ON [dbo].[scratch] TO [public]  
   GO  
   if exists (select * from dbo.sysobjects where id = object_id(N'[dbo].[sp_txnProc]') and OBJECTPROPERTY(id, N'IsProcedure') = 1)  
   drop procedure [dbo].[sp_txnProc]  
   GO  
   CREATE PROCEDURE [dbo].[sp_txnProc] @Data nvarchar (4000)  
   AS   
   INSERT scratch ( msg ) values ( @Data )  
   GO  
   GRANT EXECUTE ON [dbo].[sp_txnProc] TO [public]  
   GO  
   ```  

4. <span data-ttu-id="3fa47-249">在中[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**发送端口**节点中，选择**TxnSendPort1**发送端口，然后选择**启动**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-249">In [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the **Send Ports** node, select the **TxnSendPort1** send port, and select **Start**.</span></span>  

5. <span data-ttu-id="3fa47-250">在中[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**ReceiveLocations**节点中，选择**TxnReceiveLocation1**接收位置，然后选择**启用**。</span><span class="sxs-lookup"><span data-stu-id="3fa47-250">In [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the **ReceiveLocations** node, select the **TxnReceiveLocation1** receive location, and then select **Enable**.</span></span>  

6. <span data-ttu-id="3fa47-251">在启用该接收位置后，它将在指定的时间间隔自动轮询数据库以获得数据。</span><span class="sxs-lookup"><span data-stu-id="3fa47-251">Once the receive location is enabled, it will automatically poll the database at the designated intervals for data.</span></span>  

## <a name="classes-or-methods-used-in-the-sample"></a><span data-ttu-id="3fa47-252">类或方法的示例中使用</span><span class="sxs-lookup"><span data-stu-id="3fa47-252">Classes or Methods Used in the sample</span></span>  
* <span data-ttu-id="3fa47-253">IBTTransmitterBatch 接口 (COM)</span><span class="sxs-lookup"><span data-stu-id="3fa47-253">IBTTransmitterBatch Interface (COM)</span></span>

* <span data-ttu-id="3fa47-254">IBTTransportProxy 接口 (COM)</span><span class="sxs-lookup"><span data-stu-id="3fa47-254">IBTTransportProxy Interface (COM)</span></span>

<span data-ttu-id="3fa47-255">介绍了这些方法[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="3fa47-255">These methods are described [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 

## <a name="see-also"></a><span data-ttu-id="3fa47-256">请参阅</span><span class="sxs-lookup"><span data-stu-id="3fa47-256">See Also</span></span>  
 <span data-ttu-id="3fa47-257">[适配器示例-开发](../core/adapter-samples-development.md) </span><span class="sxs-lookup"><span data-stu-id="3fa47-257">[Adapter Samples - Development](../core/adapter-samples-development.md) </span></span>  
 [<span data-ttu-id="3fa47-258">注册适配器</span><span class="sxs-lookup"><span data-stu-id="3fa47-258">Registering an Adapter</span></span>](../core/registering-an-adapter.md)