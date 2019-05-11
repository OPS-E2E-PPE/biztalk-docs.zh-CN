---
title: 连接到 Visual Studio 中使用适配器服务外接程序使用的 SQL Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d4fa2bd-ac9e-41b1-8fea-e6a41cbfd1a2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5154abeef4b9b872b1ef8a6c4cc5c517f202a4d1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369944"
---
# <a name="connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in"></a><span data-ttu-id="c22bf-102">连接到 Visual Studio 中使用适配器服务外接程序使用的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="c22bf-102">Connect to SQL Server in Visual Studio using the Consume Adapter Service Add-in</span></span>
<span data-ttu-id="c22bf-103">[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]安装时安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c22bf-103">The [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] is installed when you install [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="c22bf-104">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]加载在计算机上安装的所有 WCF 自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="c22bf-104">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] loads all the WCF-Custom bindings installed on the computer.</span></span> <span data-ttu-id="c22bf-105">若要连接到使用基于 WCF 的 SQL Server[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在 BizTalk 项目中，必须使用**sqlbinding**。</span><span class="sxs-lookup"><span data-stu-id="c22bf-105">To connect to SQL Server using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in a BizTalk project, you must use the **sqlbinding**.</span></span>  

 <span data-ttu-id="c22bf-106">本主题说明了如何使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c22bf-106">This topic provides instructions on how to use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  

## <a name="connecting-to-sql-server-using-consume-adapter-service-add-in"></a><span data-ttu-id="c22bf-107">连接到 SQL Server 使用使用适配器服务外接程序</span><span class="sxs-lookup"><span data-stu-id="c22bf-107">Connecting to SQL Server Using Consume Adapter Service Add-in</span></span>  
 <span data-ttu-id="c22bf-108">执行以下步骤连接到 SQL Server 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c22bf-108">Perform the following steps to connect to SQL Server using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  

#### <a name="to-connect-to-sql-server"></a><span data-ttu-id="c22bf-109">若要连接到 SQL Server</span><span class="sxs-lookup"><span data-stu-id="c22bf-109">To connect to SQL Server</span></span>  

1. <span data-ttu-id="c22bf-110">若要使用连接[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]BizTalk 解决方案中：</span><span class="sxs-lookup"><span data-stu-id="c22bf-110">To connect using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] in a BizTalk solution:</span></span>  

   1. <span data-ttu-id="c22bf-111">创建 BizTalk 项目使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c22bf-111">Create a BizTalk project using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  

   2. <span data-ttu-id="c22bf-112">右键单击解决方案资源管理器中的项目名称，指向**外**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="c22bf-112">Right-click the project name in Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  

   3. <span data-ttu-id="c22bf-113">在中**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c22bf-113">In the **Add Generated Items** dialog box, do the following:</span></span>  


      |    <span data-ttu-id="c22bf-114">使用此选项</span><span class="sxs-lookup"><span data-stu-id="c22bf-114">Use this</span></span>    |             <span data-ttu-id="c22bf-115">执行的操作</span><span class="sxs-lookup"><span data-stu-id="c22bf-115">To do this</span></span>             |
      |----------------|------------------------------------|
      | <span data-ttu-id="c22bf-116">**类别**</span><span class="sxs-lookup"><span data-stu-id="c22bf-116">**Categories**</span></span> | <span data-ttu-id="c22bf-117">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="c22bf-117">Click **Consume Adapter Service**.</span></span> |
      | <span data-ttu-id="c22bf-118">**模板**</span><span class="sxs-lookup"><span data-stu-id="c22bf-118">**Templates**</span></span>  | <span data-ttu-id="c22bf-119">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="c22bf-119">Click **Consume Adapter Service**.</span></span> |


   4. <span data-ttu-id="c22bf-120">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="c22bf-120">Click **Add**.</span></span> <span data-ttu-id="c22bf-121">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]随即打开。</span><span class="sxs-lookup"><span data-stu-id="c22bf-121">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] opens.</span></span>  

2. <span data-ttu-id="c22bf-122">从**选择绑定**下拉列表中，选择**sqlBinding**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="c22bf-122">From the **Select a binding** drop-down list, select **sqlBinding**, and then click **Configure**.</span></span>  

3. <span data-ttu-id="c22bf-123">在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表中，执行下列任一操作：</span><span class="sxs-lookup"><span data-stu-id="c22bf-123">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential  type** drop-down list, do one of the following:</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="c22bf-124">与你登录的 Windows 用户如果要连接到 SQL Server 使用 Windows 身份验证，必须为 SQL Server 中所述添加[连接到 SQL Server 与 SQL 适配器使用 Windows 身份验证](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="c22bf-124">If you are connecting to SQL Server using Windows Authentication, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  

   |  <span data-ttu-id="c22bf-125">单击此选项</span><span class="sxs-lookup"><span data-stu-id="c22bf-125">Click this</span></span>  |                                                                                                                                                               <span data-ttu-id="c22bf-126">执行的操作</span><span class="sxs-lookup"><span data-stu-id="c22bf-126">To do this</span></span>                                                                                                                                                               |
   |--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   <span data-ttu-id="c22bf-127">**无**</span><span class="sxs-lookup"><span data-stu-id="c22bf-127">**None**</span></span>   |                                                                                                                                         <span data-ttu-id="c22bf-128">使用 Windows 身份验证连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="c22bf-128">Connect to SQL Server by using Windows authentication.</span></span>                                                                                                                                         |
   | <span data-ttu-id="c22bf-129">**Windows**</span><span class="sxs-lookup"><span data-stu-id="c22bf-129">**Windows**</span></span>  |                                                                                                                                         <span data-ttu-id="c22bf-130">使用 Windows 身份验证连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="c22bf-130">Connect to SQL Server by using Windows authentication.</span></span>                                                                                                                                         |
   | <span data-ttu-id="c22bf-131">**用户名**</span><span class="sxs-lookup"><span data-stu-id="c22bf-131">**Username**</span></span> | <span data-ttu-id="c22bf-132">指定的用户名和密码以连接到 SQL Server 通过指定 SQL Server 数据库中定义的用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="c22bf-132">Specify the user name and password to connect to SQL Server by specifying credentials for a user defined in SQL Server database.</span></span> <span data-ttu-id="c22bf-133">请注意，用户名和密码是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="c22bf-133">Note that the user name and password are case-sensitive.</span></span> <span data-ttu-id="c22bf-134">**注意：** 如果将保留**用户名**并**密码**字段留为空白，适配器将连接到 SQL Server 使用 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c22bf-134">**Note:**  If you leave the **User name** and **Password** fields as blank, the adapter connects to SQL Server using Windows authentication.</span></span> |


4. <span data-ttu-id="c22bf-135">单击**URI 属性**选项卡，然后指定连接参数的值。</span><span class="sxs-lookup"><span data-stu-id="c22bf-135">Click the **URI Properties** tab, and then specify values for the connection parameters.</span></span> <span data-ttu-id="c22bf-136">有关详细信息的连接 URI 对于[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[创建的 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="c22bf-136">For more information about the connection URI for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Create the SQL Server connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="c22bf-137">如果连接参数包含任何保留的字符，则必须指定其作为-处于**URI 属性**选项卡上，即，而无需使用任何转义符。</span><span class="sxs-lookup"><span data-stu-id="c22bf-137">If the connection parameters contain any reserved characters, you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="c22bf-138">但是，如果指定的 URI 中直接**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用正确的转义字符。</span><span class="sxs-lookup"><span data-stu-id="c22bf-138">However, if you specify the URI directly in the **Configure a URI** field and the connection parameters contain reserved characters, you must specify the connection parameters using proper escape characters.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="c22bf-139">如果未指定任何值在 URI 的属性选项卡中，[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]会将 URI 设置为`mssql://.//`。</span><span class="sxs-lookup"><span data-stu-id="c22bf-139">If you do not specify any values in the URI property tab, the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] puts the URI as `mssql://.//`.</span></span> <span data-ttu-id="c22bf-140">在这种情况下，适配器连接到的默认数据库和本地计算机上的默认数据库实例。</span><span class="sxs-lookup"><span data-stu-id="c22bf-140">In such a case, the adapter connects to the default database and the default database instance on the local computer.</span></span>  

5. <span data-ttu-id="c22bf-141">单击**绑定属性**选项卡，然后指定绑定属性的值，如果你想要针对的操作，任何需要。</span><span class="sxs-lookup"><span data-stu-id="c22bf-141">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span>  

6. <span data-ttu-id="c22bf-142">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="c22bf-142">Click **OK**.</span></span>  

7. <span data-ttu-id="c22bf-143">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="c22bf-143">Click **Connect**.</span></span> <span data-ttu-id="c22bf-144">建立连接后，连接状态显示为**已连接**。</span><span class="sxs-lookup"><span data-stu-id="c22bf-144">After the connection is established, the connection status is shown as **Connected**.</span></span>  

    <span data-ttu-id="c22bf-145">下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。</span><span class="sxs-lookup"><span data-stu-id="c22bf-145">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span>  

    <span data-ttu-id="c22bf-146">![连接到 SQL Server](../../adapters-and-accelerators/adapter-sql/media/661adb8a-5050-44d5-8db8-fdf0fe530b40.gif "661adb8a-5050-44d5-8db8-fdf0fe530b40")</span><span class="sxs-lookup"><span data-stu-id="c22bf-146">![Connect to SQL Server](../../adapters-and-accelerators/adapter-sql/media/661adb8a-5050-44d5-8db8-fdf0fe530b40.gif "661adb8a-5050-44d5-8db8-fdf0fe530b40")</span></span>  

    <span data-ttu-id="c22bf-147">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]显示包含可以在 SQL Server 执行各种操作的不同节点。</span><span class="sxs-lookup"><span data-stu-id="c22bf-147">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] displays different nodes containing various operations that can be performed on SQL Server.</span></span> <span data-ttu-id="c22bf-148">例如，**过程**节点包含可用于连接到的数据库的所有过程。</span><span class="sxs-lookup"><span data-stu-id="c22bf-148">For example, the **Procedures** node contains all the procedures available for the database you connected to.</span></span> <span data-ttu-id="c22bf-149">同样，**表**节点包含在连接到数据库和可以对表执行的操作的所有表。</span><span class="sxs-lookup"><span data-stu-id="c22bf-149">Similarly, the **Tables** node contains all the tables in the database you connected to, and the operations that can be performed on a table.</span></span> <span data-ttu-id="c22bf-150">有关这些节点的详细信息，请参阅[元数据节点 Id](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md)。</span><span class="sxs-lookup"><span data-stu-id="c22bf-150">For more information about these nodes, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="c22bf-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="c22bf-151">See Also</span></span>  
 [<span data-ttu-id="c22bf-152">连接到 Visual Studio 中使用适配器服务外接程序使用的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="c22bf-152">Connect to SQL Server in Visual Studio using the Consume Adapter Service Add-in</span></span>](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)