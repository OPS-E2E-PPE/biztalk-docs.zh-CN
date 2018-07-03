---
title: 连接到 SQL Server Visual Studio 中使用添加适配器服务引用插件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fc3b824-d20b-4531-81f3-89b4a1ff3216
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9998acf89bd036230dceb3a06f950497677490b9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018257"
---
# <a name="connect-to-sql-server-in-visual-studio-using-add-adapter-service-reference-plug-in"></a><span data-ttu-id="b252a-102">连接到 SQL Server Visual Studio 中使用添加适配器服务引用插件</span><span class="sxs-lookup"><span data-stu-id="b252a-102">Connect to SQL Server in Visual Studio Using Add Adapter Service Reference Plug-in</span></span>
<span data-ttu-id="b252a-103">若要连接到 SQL Server 使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在.NET 编程解决方案中，必须使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b252a-103">To connect to SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in a .NET programming solution, you must use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span> <span data-ttu-id="b252a-104">本主题说明了如何使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b252a-104">This topic provides instructions on how to use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  

## <a name="connecting-to-sql-server-using-add-adapter-service-reference-plug-in"></a><span data-ttu-id="b252a-105">连接到 SQL Server 使用添加适配器服务引用插件</span><span class="sxs-lookup"><span data-stu-id="b252a-105">Connecting to SQL Server Using Add Adapter Service Reference Plug-in</span></span>  
 <span data-ttu-id="b252a-106">执行以下步骤连接到 SQL Server 使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b252a-106">Perform the following steps to connect to SQL Server using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  

#### <a name="to-connect-to-sql-server"></a><span data-ttu-id="b252a-107">若要连接到 SQL Server</span><span class="sxs-lookup"><span data-stu-id="b252a-107">To connect to SQL Server</span></span>  

1. <span data-ttu-id="b252a-108">若要使用连接[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]编程解决方案中：</span><span class="sxs-lookup"><span data-stu-id="b252a-108">To connect using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] in a programming solution:</span></span>  

   1. <span data-ttu-id="b252a-109">创建的项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b252a-109">Create a project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  

   2. <span data-ttu-id="b252a-110">右键单击解决方案资源管理器中的项目，然后单击**添加适配器服务引用**。</span><span class="sxs-lookup"><span data-stu-id="b252a-110">Right-click the project in Solution Explorer, and then click **Add Adapter Service Reference**.</span></span> <span data-ttu-id="b252a-111">此时[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]会打开。</span><span class="sxs-lookup"><span data-stu-id="b252a-111">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] opens.</span></span>  

2. <span data-ttu-id="b252a-112">从**选择绑定**下拉列表中，选择**sqlBinding**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="b252a-112">From the **Select a binding** drop-down list, select **sqlBinding**, and then click **Configure**.</span></span>  

3. <span data-ttu-id="b252a-113">在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表中，执行下列任一操作：</span><span class="sxs-lookup"><span data-stu-id="b252a-113">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential  type** drop-down list, do one of the following:</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="b252a-114">与你登录的 Windows 用户如果要连接到 SQL Server 使用 Windows 身份验证，必须为 SQL Server 中所述添加[连接到 SQL Server 与 SQL 适配器使用 Windows 身份验证](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="b252a-114">If you are connecting to SQL Server using Windows Authentication, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  

   |  <span data-ttu-id="b252a-115">单击此选项</span><span class="sxs-lookup"><span data-stu-id="b252a-115">Click this</span></span>  |                                                                                                                                                               <span data-ttu-id="b252a-116">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b252a-116">To do this</span></span>                                                                                                                                                               |
   |--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   <span data-ttu-id="b252a-117">**无**</span><span class="sxs-lookup"><span data-stu-id="b252a-117">**None**</span></span>   |                                                                                                                                         <span data-ttu-id="b252a-118">使用 Windows 身份验证连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b252a-118">Connect to SQL Server by using Windows authentication.</span></span>                                                                                                                                         |
   | <span data-ttu-id="b252a-119">**Windows**</span><span class="sxs-lookup"><span data-stu-id="b252a-119">**Windows**</span></span>  |                                                                                                                                         <span data-ttu-id="b252a-120">使用 Windows 身份验证连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b252a-120">Connect to SQL Server by using Windows authentication.</span></span>                                                                                                                                         |
   | <span data-ttu-id="b252a-121">**用户名**</span><span class="sxs-lookup"><span data-stu-id="b252a-121">**Username**</span></span> | <span data-ttu-id="b252a-122">通过指定 SQL Server 数据库中定义的用户凭据，指定用于连接 SQL Server 的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="b252a-122">Specify the user name and password to connect to SQL Server by specifying credentials for a user defined in SQL Server database.</span></span> <span data-ttu-id="b252a-123">请注意，用户名和密码区分大小写。</span><span class="sxs-lookup"><span data-stu-id="b252a-123">Note that the user name and password are case-sensitive.</span></span> <span data-ttu-id="b252a-124">**注意：** 如果将保留**用户名**并**密码**字段留为空白，适配器将连接到 SQL Server 使用 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="b252a-124">**Note:**  If you leave the **User name** and **Password** fields as blank, the adapter connects to SQL Server using Windows authentication.</span></span> |


4. <span data-ttu-id="b252a-125">单击**URI 属性**选项卡，然后指定连接参数的值。</span><span class="sxs-lookup"><span data-stu-id="b252a-125">Click the **URI Properties** tab, and then specify values for the connection parameters.</span></span> <span data-ttu-id="b252a-126">有关详细信息的连接 URI 对于[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[创建的 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="b252a-126">For more information about the connection URI for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Create the SQL Server connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="b252a-127">如果连接参数包含任何保留的字符，则必须指定其作为-处于**URI 属性**选项卡上，即，而无需使用任何转义符。</span><span class="sxs-lookup"><span data-stu-id="b252a-127">If the connection parameters contain any reserved characters, you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="b252a-128">但是，如果指定的 URI 中直接**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用正确的转义字符。</span><span class="sxs-lookup"><span data-stu-id="b252a-128">However, if you specify the URI directly in the **Configure a URI** field and the connection parameters contain reserved characters, you must specify the connection parameters using proper escape characters.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="b252a-129">如果不在“URI 属性”选项卡中指定任何值，[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]会将 URI 设置为 `mssql://.//`。</span><span class="sxs-lookup"><span data-stu-id="b252a-129">If you do not specify any values in the URI property tab, the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] puts the URI as `mssql://.//`.</span></span> <span data-ttu-id="b252a-130">在此类情况下，适配器将连接至本地计算机上的默认数据库和默认数据库实例。</span><span class="sxs-lookup"><span data-stu-id="b252a-130">In such a case, the adapter connects to the default database and the default database instance on the local computer.</span></span>  

5. <span data-ttu-id="b252a-131">单击**绑定属性**选项卡，然后指定绑定属性的值，如果你想要针对的操作，任何需要。</span><span class="sxs-lookup"><span data-stu-id="b252a-131">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span>  

6. <span data-ttu-id="b252a-132">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="b252a-132">Click **OK**.</span></span>  

7. <span data-ttu-id="b252a-133">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="b252a-133">Click **Connect**.</span></span> <span data-ttu-id="b252a-134">建立连接后，连接状态显示为**已连接**。</span><span class="sxs-lookup"><span data-stu-id="b252a-134">After the connection is established, the connection status is shown as **Connected**.</span></span>  

    <span data-ttu-id="b252a-135">下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。</span><span class="sxs-lookup"><span data-stu-id="b252a-135">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span> <span data-ttu-id="b252a-136">图形用户界面是适用于[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b252a-136">The graphical user interface is same for the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  

    <span data-ttu-id="b252a-137">![连接到 SQL Server](../../adapters-and-accelerators/adapter-sql/media/661adb8a-5050-44d5-8db8-fdf0fe530b40.gif "661adb8a-5050-44d5-8db8-fdf0fe530b40")</span><span class="sxs-lookup"><span data-stu-id="b252a-137">![Connect to SQL Server](../../adapters-and-accelerators/adapter-sql/media/661adb8a-5050-44d5-8db8-fdf0fe530b40.gif "661adb8a-5050-44d5-8db8-fdf0fe530b40")</span></span>  

    <span data-ttu-id="b252a-138">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]显示包含可以在 SQL Server 执行各种操作的不同节点。</span><span class="sxs-lookup"><span data-stu-id="b252a-138">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] displays different nodes containing various operations that can be performed on SQL Server.</span></span> <span data-ttu-id="b252a-139">例如，**过程**节点包含可用于连接到的数据库的所有过程。</span><span class="sxs-lookup"><span data-stu-id="b252a-139">For example, the **Procedures** node contains all the procedures available for the database you connected to.</span></span> <span data-ttu-id="b252a-140">同样，**表**节点包含在连接到数据库和可以对表执行的操作的所有表。</span><span class="sxs-lookup"><span data-stu-id="b252a-140">Similarly, the **Tables** node contains all the tables in the database you connected to, and the operations that can be performed on a table.</span></span> <span data-ttu-id="b252a-141">有关这些节点的详细信息，请参阅[元数据节点 Id](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md)。</span><span class="sxs-lookup"><span data-stu-id="b252a-141">For more information about these nodes, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="b252a-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="b252a-142">See Also</span></span>  
 [<span data-ttu-id="b252a-143">连接到 Visual Studio 中使用适配器服务外接程序使用的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="b252a-143">Connect to SQL Server in Visual Studio using the Consume Adapter Service Add-in</span></span>](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)