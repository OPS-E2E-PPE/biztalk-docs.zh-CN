---
title: "连接到使用适配器服务外接程序使用的 Visual Studio 中的 SQL Server |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d4fa2bd-ac9e-41b1-8fea-e6a41cbfd1a2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69ccf497c9546f0695565e3e9f46ec2536b42ef8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in"></a><span data-ttu-id="8af99-102">连接到使用适配器服务外接程序使用的 Visual Studio 中的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="8af99-102">Connect to SQL Server in Visual Studio using the Consume Adapter Service Add-in</span></span>
<span data-ttu-id="8af99-103">[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]安装时安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8af99-103">The [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] is installed when you install [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="8af99-104">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]加载在计算机上安装的所有 WCF 自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="8af99-104">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] loads all the WCF-Custom bindings installed on the computer.</span></span> <span data-ttu-id="8af99-105">若要连接到 SQL Server 使用基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在 BizTalk 项目，你必须使用**sqlbinding**。</span><span class="sxs-lookup"><span data-stu-id="8af99-105">To connect to SQL Server using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in a BizTalk project, you must use the **sqlbinding**.</span></span>  
  
 <span data-ttu-id="8af99-106">本主题将说明了如何使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8af99-106">This topic provides instructions on how to use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  
  
## <a name="connecting-to-sql-server-using-consume-adapter-service-add-in"></a><span data-ttu-id="8af99-107">连接到 SQL Server 使用使用适配器服务外接程序</span><span class="sxs-lookup"><span data-stu-id="8af99-107">Connecting to SQL Server Using Consume Adapter Service Add-in</span></span>  
 <span data-ttu-id="8af99-108">执行以下步骤以连接到 SQL Server 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8af99-108">Perform the following steps to connect to SQL Server using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  
  
#### <a name="to-connect-to-sql-server"></a><span data-ttu-id="8af99-109">若要连接到 SQL Server</span><span class="sxs-lookup"><span data-stu-id="8af99-109">To connect to SQL Server</span></span>  
  
1.  <span data-ttu-id="8af99-110">若要使用连接[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]BizTalk 解决方案中：</span><span class="sxs-lookup"><span data-stu-id="8af99-110">To connect using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] in a BizTalk solution:</span></span>  
  
    1.  <span data-ttu-id="8af99-111">创建 BizTalk 项目使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8af99-111">Create a BizTalk project using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
    2.  <span data-ttu-id="8af99-112">右键单击解决方案资源管理器中的项目名称，指向**添加**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="8af99-112">Right-click the project name in Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
    3.  <span data-ttu-id="8af99-113">在**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8af99-113">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
        |<span data-ttu-id="8af99-114">使用此选项</span><span class="sxs-lookup"><span data-stu-id="8af99-114">Use this</span></span>|<span data-ttu-id="8af99-115">执行的操作</span><span class="sxs-lookup"><span data-stu-id="8af99-115">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="8af99-116">**类别**</span><span class="sxs-lookup"><span data-stu-id="8af99-116">**Categories**</span></span>|<span data-ttu-id="8af99-117">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="8af99-117">Click **Consume Adapter Service**.</span></span>|  
        |<span data-ttu-id="8af99-118">**模板**</span><span class="sxs-lookup"><span data-stu-id="8af99-118">**Templates**</span></span>|<span data-ttu-id="8af99-119">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="8af99-119">Click **Consume Adapter Service**.</span></span>|  
  
    4.  <span data-ttu-id="8af99-120">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="8af99-120">Click **Add**.</span></span> <span data-ttu-id="8af99-121">此时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]会打开。</span><span class="sxs-lookup"><span data-stu-id="8af99-121">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] opens.</span></span>  
  
2.  <span data-ttu-id="8af99-122">从**选择的绑定**下拉列表中，选择**sqlBinding**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="8af99-122">From the **Select a binding** drop-down list, select **sqlBinding**, and then click **Configure**.</span></span>  
  
3.  <span data-ttu-id="8af99-123">在**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表中，执行下列其中一项：</span><span class="sxs-lookup"><span data-stu-id="8af99-123">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential  type** drop-down list, do one of the following:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8af99-124">中所述，如果你要连接到 SQL Server 使用 Windows 身份验证，必须到 SQL Server 中添加与你登录的 Windows 用户[连接到 SQL Server 和 SQL 适配器一起使用 Windows 身份验证](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="8af99-124">If you are connecting to SQL Server using Windows Authentication, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
    |<span data-ttu-id="8af99-125">单击此链接</span><span class="sxs-lookup"><span data-stu-id="8af99-125">Click this</span></span>|<span data-ttu-id="8af99-126">执行的操作</span><span class="sxs-lookup"><span data-stu-id="8af99-126">To do this</span></span>|  
    |----------------|----------------|  
    |<span data-ttu-id="8af99-127">**无**</span><span class="sxs-lookup"><span data-stu-id="8af99-127">**None**</span></span>|<span data-ttu-id="8af99-128">使用 Windows 身份验证连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="8af99-128">Connect to SQL Server by using Windows authentication.</span></span>|  
    |<span data-ttu-id="8af99-129">**Windows**</span><span class="sxs-lookup"><span data-stu-id="8af99-129">**Windows**</span></span>|<span data-ttu-id="8af99-130">使用 Windows 身份验证连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="8af99-130">Connect to SQL Server by using Windows authentication.</span></span>|  
    |<span data-ttu-id="8af99-131">**用户名**</span><span class="sxs-lookup"><span data-stu-id="8af99-131">**Username**</span></span>|<span data-ttu-id="8af99-132">通过指定 SQL Server 数据库中定义的用户凭据，指定用于连接 SQL Server 的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="8af99-132">Specify the user name and password to connect to SQL Server by specifying credentials for a user defined in SQL Server database.</span></span> <span data-ttu-id="8af99-133">请注意，用户名和密码区分大小写。</span><span class="sxs-lookup"><span data-stu-id="8af99-133">Note that the user name and password are case-sensitive.</span></span> <span data-ttu-id="8af99-134">**注意：**如果你离开**用户名**和**密码**为空白字段，该适配器将连接到 SQL Server 使用 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="8af99-134">**Note:**  If you leave the **User name** and **Password** fields as blank, the adapter connects to SQL Server using Windows authentication.</span></span>|  
  
4.  <span data-ttu-id="8af99-135">单击**URI 属性**选项卡上，然后指定连接参数的值。</span><span class="sxs-lookup"><span data-stu-id="8af99-135">Click the **URI Properties** tab, and then specify values for the connection parameters.</span></span> <span data-ttu-id="8af99-136">有关连接 URI 的详细信息为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="8af99-136">For more information about the connection URI for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Create the SQL Server connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8af99-137">如果连接参数包含任何保留的字符，则必须指定它们作为-处于**URI 属性**选项卡上，即，而无需使用任何转义字符。</span><span class="sxs-lookup"><span data-stu-id="8af99-137">If the connection parameters contain any reserved characters, you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="8af99-138">但是，如果你指定直接在 URI**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用适当的转义字符。</span><span class="sxs-lookup"><span data-stu-id="8af99-138">However, if you specify the URI directly in the **Configure a URI** field and the connection parameters contain reserved characters, you must specify the connection parameters using proper escape characters.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8af99-139">如果不在“URI 属性”选项卡中指定任何值，[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]会将 URI 设置为 `mssql://.//`。</span><span class="sxs-lookup"><span data-stu-id="8af99-139">If you do not specify any values in the URI property tab, the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] puts the URI as `mssql://.//`.</span></span> <span data-ttu-id="8af99-140">在此类情况下，适配器将连接至本地计算机上的默认数据库和默认数据库实例。</span><span class="sxs-lookup"><span data-stu-id="8af99-140">In such a case, the adapter connects to the default database and the default database instance on the local computer.</span></span>  
  
5.  <span data-ttu-id="8af99-141">单击**绑定属性**选项卡上，然后指定绑定属性的值，如果任何，所需的要设定为目标的操作。</span><span class="sxs-lookup"><span data-stu-id="8af99-141">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span>  
  
6.  <span data-ttu-id="8af99-142">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="8af99-142">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="8af99-143">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="8af99-143">Click **Connect**.</span></span> <span data-ttu-id="8af99-144">建立连接后，连接状态将显示为**已连接**。</span><span class="sxs-lookup"><span data-stu-id="8af99-144">After the connection is established, the connection status is shown as **Connected**.</span></span>  
  
     <span data-ttu-id="8af99-145">下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。</span><span class="sxs-lookup"><span data-stu-id="8af99-145">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span>  
  
     <span data-ttu-id="8af99-146">![连接到 SQL Server](../../adapters-and-accelerators/adapter-sql/media/661adb8a-5050-44d5-8db8-fdf0fe530b40.gif "661adb8a-5050-44d5-8db8-fdf0fe530b40")</span><span class="sxs-lookup"><span data-stu-id="8af99-146">![Connect to SQL Server](../../adapters-and-accelerators/adapter-sql/media/661adb8a-5050-44d5-8db8-fdf0fe530b40.gif "661adb8a-5050-44d5-8db8-fdf0fe530b40")</span></span>  
  
     <span data-ttu-id="8af99-147">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]显示包含可以在 SQL Server 执行的各种操作的不同节点。</span><span class="sxs-lookup"><span data-stu-id="8af99-147">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] displays different nodes containing various operations that can be performed on SQL Server.</span></span> <span data-ttu-id="8af99-148">例如，**过程**节点包含可用于连接到的数据库的所有过程。</span><span class="sxs-lookup"><span data-stu-id="8af99-148">For example, the **Procedures** node contains all the procedures available for the database you connected to.</span></span> <span data-ttu-id="8af99-149">同样，**表**节点包含在连接到的数据库和可以对表执行的操作中的所有表。</span><span class="sxs-lookup"><span data-stu-id="8af99-149">Similarly, the **Tables** node contains all the tables in the database you connected to, and the operations that can be performed on a table.</span></span> <span data-ttu-id="8af99-150">有关这些节点的详细信息，请参阅[元数据的节点 Id](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md)。</span><span class="sxs-lookup"><span data-stu-id="8af99-150">For more information about these nodes, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8af99-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8af99-151">See Also</span></span>  
 [<span data-ttu-id="8af99-152">连接到使用适配器服务外接程序使用的 Visual Studio 中的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="8af99-152">Connect to SQL Server in Visual Studio using the Consume Adapter Service Add-in</span></span>](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)