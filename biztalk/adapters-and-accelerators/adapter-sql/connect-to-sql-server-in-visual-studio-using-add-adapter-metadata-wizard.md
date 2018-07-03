---
title: 连接到 SQL Server Visual Studio 中使用添加适配器元数据向导 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2169722d-beba-4d96-a54b-54986ece9bf8
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6de95e2e6906a840e0e41d013f6c1e1e0a73a8d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981398"
---
# <a name="connect-to-sql-server-in-visual-studio-using-add-adapter-metadata-wizard"></a><span data-ttu-id="6602f-102">连接到 SQL Server Visual Studio 中使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="6602f-102">Connect to SQL Server in Visual Studio Using Add Adapter Metadata Wizard</span></span>
<span data-ttu-id="6602f-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]还会显示为 BizTalk 适配器，因此，您可以使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]来为你想要使用的适配器的 SQL 服务器上执行的操作生成架构。</span><span class="sxs-lookup"><span data-stu-id="6602f-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is also exposed as a BizTalk adapter and, therefore, you can use the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] to generate schema for the operations you want to perform on SQL Server using the adapter.</span></span>  

## <a name="connecting-to-sql-server-using-add-adapter-metadata-wizard"></a><span data-ttu-id="6602f-104">连接到 SQL Server 使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="6602f-104">Connecting to SQL Server Using Add Adapter Metadata Wizard</span></span>  
 <span data-ttu-id="6602f-105">执行以下步骤连接到 SQL Server 使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6602f-105">Perform the following steps to connect to SQL Server using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

#### <a name="to-connect-to-sql-server"></a><span data-ttu-id="6602f-106">若要连接到 SQL Server</span><span class="sxs-lookup"><span data-stu-id="6602f-106">To connect to SQL Server</span></span>  

1. <span data-ttu-id="6602f-107">若要使用连接[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]BizTalk 解决方案中：</span><span class="sxs-lookup"><span data-stu-id="6602f-107">To connect using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] in a BizTalk solution:</span></span>  

   1. <span data-ttu-id="6602f-108">创建 BizTalk 项目使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6602f-108">Create a BizTalk project using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  

   2. <span data-ttu-id="6602f-109">右键单击解决方案资源管理器中的项目名称，指向**外**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="6602f-109">Right-click the project name in Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  

   3. <span data-ttu-id="6602f-110">在中**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6602f-110">In the **Add Generated Items** dialog box, do the following:</span></span>  


      |    <span data-ttu-id="6602f-111">使用此选项</span><span class="sxs-lookup"><span data-stu-id="6602f-111">Use this</span></span>    |           <span data-ttu-id="6602f-112">执行的操作</span><span class="sxs-lookup"><span data-stu-id="6602f-112">To do this</span></span>            |
      |----------------|---------------------------------|
      | <span data-ttu-id="6602f-113">**类别**</span><span class="sxs-lookup"><span data-stu-id="6602f-113">**Categories**</span></span> |     <span data-ttu-id="6602f-114">单击**将适配器添加**。</span><span class="sxs-lookup"><span data-stu-id="6602f-114">Click **Add Adapter**.</span></span>      |
      | <span data-ttu-id="6602f-115">**模板**</span><span class="sxs-lookup"><span data-stu-id="6602f-115">**Templates**</span></span>  | <span data-ttu-id="6602f-116">单击**添加适配器元数据**。</span><span class="sxs-lookup"><span data-stu-id="6602f-116">Click **Add Adapter Metadata**.</span></span> |


   4. <span data-ttu-id="6602f-117">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="6602f-117">Click **Add**.</span></span> <span data-ttu-id="6602f-118">此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。</span><span class="sxs-lookup"><span data-stu-id="6602f-118">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  

   5. <span data-ttu-id="6602f-119">在添加适配器向导中，选择**WCF-SQL**。</span><span class="sxs-lookup"><span data-stu-id="6602f-119">In the Add Adapter Wizard, select **WCF-SQL**.</span></span> <span data-ttu-id="6602f-120">选择的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装和 BizTalk 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="6602f-120">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  

      > [!IMPORTANT]
      >  <span data-ttu-id="6602f-121">如果已配置 BizTalk 中的 WCF SQL 端口，选择从端口**端口**列表。</span><span class="sxs-lookup"><span data-stu-id="6602f-121">If you already have a WCF-SQL port configured in BizTalk, select the port from the **Port** list.</span></span>  

   6. <span data-ttu-id="6602f-122">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="6602f-122">Click **Next**.</span></span>  

2. <span data-ttu-id="6602f-123">从**选择绑定**下拉列表中，选择**sqlBinding**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="6602f-123">From the **Select a binding** drop-down list, select **sqlBinding**, and then click **Configure**.</span></span>  

3. <span data-ttu-id="6602f-124">在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表中，执行下列任一操作：</span><span class="sxs-lookup"><span data-stu-id="6602f-124">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential  type** drop-down list, do one of the following:</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="6602f-125">与你登录的 Windows 用户如果要连接到 SQL Server 使用 Windows 身份验证，必须为 SQL Server 中所述添加[连接到 SQL Server 与 SQL 适配器使用 Windows 身份验证](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="6602f-125">If you are connecting to SQL Server using Windows Authentication, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  

   |  <span data-ttu-id="6602f-126">单击此选项</span><span class="sxs-lookup"><span data-stu-id="6602f-126">Click this</span></span>  |                                                                                                                                                               <span data-ttu-id="6602f-127">执行的操作</span><span class="sxs-lookup"><span data-stu-id="6602f-127">To do this</span></span>                                                                                                                                                               |
   |--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   <span data-ttu-id="6602f-128">**无**</span><span class="sxs-lookup"><span data-stu-id="6602f-128">**None**</span></span>   |                                                                                                                                         <span data-ttu-id="6602f-129">使用 Windows 身份验证连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="6602f-129">Connect to SQL Server by using Windows authentication.</span></span>                                                                                                                                         |
   | <span data-ttu-id="6602f-130">**Windows**</span><span class="sxs-lookup"><span data-stu-id="6602f-130">**Windows**</span></span>  |                                                                                                                                         <span data-ttu-id="6602f-131">使用 Windows 身份验证连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="6602f-131">Connect to SQL Server by using Windows authentication.</span></span>                                                                                                                                         |
   | <span data-ttu-id="6602f-132">**用户名**</span><span class="sxs-lookup"><span data-stu-id="6602f-132">**Username**</span></span> | <span data-ttu-id="6602f-133">通过指定 SQL Server 数据库中定义的用户凭据，指定用于连接 SQL Server 的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="6602f-133">Specify the user name and password to connect to SQL Server by specifying credentials for a user defined in SQL Server database.</span></span> <span data-ttu-id="6602f-134">请注意，用户名和密码区分大小写。</span><span class="sxs-lookup"><span data-stu-id="6602f-134">Note that the user name and password are case-sensitive.</span></span> <span data-ttu-id="6602f-135">**注意：** 如果将保留**用户名**并**密码**字段留为空白，适配器将连接到 SQL Server 使用 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="6602f-135">**Note:**  If you leave the **User name** and **Password** fields as blank, the adapter connects to SQL Server using Windows authentication.</span></span> |


4. <span data-ttu-id="6602f-136">单击**URI 属性**选项卡，然后指定连接参数的值。</span><span class="sxs-lookup"><span data-stu-id="6602f-136">Click the **URI Properties** tab, and then specify values for the connection parameters.</span></span> <span data-ttu-id="6602f-137">有关详细信息的连接 URI 对于[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[创建的 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="6602f-137">For more information about the connection URI for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Create the SQL Server connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="6602f-138">如果连接参数包含任何保留的字符，则必须指定其作为-处于**URI 属性**选项卡上，即，而无需使用任何转义符。</span><span class="sxs-lookup"><span data-stu-id="6602f-138">If the connection parameters contain any reserved characters, you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="6602f-139">但是，如果指定的 URI 中直接**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用正确的转义字符。</span><span class="sxs-lookup"><span data-stu-id="6602f-139">However, if you specify the URI directly in the **Configure a URI** field and the connection parameters contain reserved characters, you must specify the connection parameters using proper escape characters.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="6602f-140">如果不在“URI 属性”选项卡中指定任何值，[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]会将 URI 设置为 `mssql://.//`。</span><span class="sxs-lookup"><span data-stu-id="6602f-140">If you do not specify any values in the URI property tab, the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] puts the URI as `mssql://.//`.</span></span> <span data-ttu-id="6602f-141">在此类情况下，适配器将连接至本地计算机上的默认数据库和默认数据库实例。</span><span class="sxs-lookup"><span data-stu-id="6602f-141">In such a case, the adapter connects to the default database and the default database instance on the local computer.</span></span>  

5. <span data-ttu-id="6602f-142">单击**绑定属性**选项卡，然后指定绑定属性的值，如果你想要针对的操作，任何需要。</span><span class="sxs-lookup"><span data-stu-id="6602f-142">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="6602f-143">有关绑定属性，请参阅详细信息[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="6602f-143">For more information about binding properties see, [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="6602f-144">如果您正在生成元数据中使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]并且选择了现有 WCF-SQL 发送端口，不需要指定绑定属性。</span><span class="sxs-lookup"><span data-stu-id="6602f-144">If you are generating metadata using [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] and you selected an existing WCF-SQL send port, you need not specify the binding properties.</span></span> <span data-ttu-id="6602f-145">绑定属性是从发送端口配置中选取。</span><span class="sxs-lookup"><span data-stu-id="6602f-145">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="6602f-146">但是，您可以选择指定如果任何，则需要在设计时的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="6602f-146">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="6602f-147">在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。</span><span class="sxs-lookup"><span data-stu-id="6602f-147">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="6602f-148">但是，在运行时指定的发送端口配置中的绑定属性的值将适用。</span><span class="sxs-lookup"><span data-stu-id="6602f-148">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  

6. <span data-ttu-id="6602f-149">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="6602f-149">Click **OK**.</span></span>  

7. <span data-ttu-id="6602f-150">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="6602f-150">Click **Connect**.</span></span> <span data-ttu-id="6602f-151">建立连接后，连接状态显示为**已连接**。</span><span class="sxs-lookup"><span data-stu-id="6602f-151">After the connection is established, the connection status is shown as **Connected**.</span></span>  

    <span data-ttu-id="6602f-152">下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。</span><span class="sxs-lookup"><span data-stu-id="6602f-152">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span> <span data-ttu-id="6602f-153">图形用户界面是适用于[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6602f-153">The graphical user interface is same for the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

    <span data-ttu-id="6602f-154">![连接到 SQL Server](../../adapters-and-accelerators/adapter-sql/media/661adb8a-5050-44d5-8db8-fdf0fe530b40.gif "661adb8a-5050-44d5-8db8-fdf0fe530b40")</span><span class="sxs-lookup"><span data-stu-id="6602f-154">![Connect to SQL Server](../../adapters-and-accelerators/adapter-sql/media/661adb8a-5050-44d5-8db8-fdf0fe530b40.gif "661adb8a-5050-44d5-8db8-fdf0fe530b40")</span></span>  

    <span data-ttu-id="6602f-155">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]显示包含可以在 SQL Server 执行各种操作的不同节点。</span><span class="sxs-lookup"><span data-stu-id="6602f-155">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] displays different nodes containing various operations that can be performed on SQL Server.</span></span> <span data-ttu-id="6602f-156">例如，**过程**节点包含可用于连接到的数据库的所有过程。</span><span class="sxs-lookup"><span data-stu-id="6602f-156">For example, the **Procedures** node contains all the procedures available for the database you connected to.</span></span> <span data-ttu-id="6602f-157">同样，**表**节点包含在连接到数据库和可以对表执行的操作的所有表。</span><span class="sxs-lookup"><span data-stu-id="6602f-157">Similarly, the **Tables** node contains all the tables in the database you connected to, and the operations that can be performed on a table.</span></span> <span data-ttu-id="6602f-158">有关这些节点的详细信息，请参阅[元数据节点 Id](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md)。</span><span class="sxs-lookup"><span data-stu-id="6602f-158">For more information about these nodes, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="6602f-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="6602f-159">See Also</span></span>  
 [<span data-ttu-id="6602f-160">连接到 Visual Studio 中使用适配器服务外接程序使用的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="6602f-160">Connect to SQL Server in Visual Studio using the Consume Adapter Service Add-in</span></span>](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)