---
title: 配置 SQL 适配器的连接 URI |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6460b22-48e4-4b7e-b82e-151e7dab1e09
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9959a88f9799730cb60d2b05358f226b31d0f84c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226789"
---
# <a name="configure-the-connection-uri-for-the-sql-adapter"></a><span data-ttu-id="b7b75-102">配置 SQL 适配器的连接 URI</span><span class="sxs-lookup"><span data-stu-id="b7b75-102">Configure the connection URI for the SQL adapter</span></span>
<span data-ttu-id="b7b75-103">连接 URI 是包含连接到 SQL Server 所需的参数的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="b7b75-103">A connection URI is a connection string that contains parameters required to connect to SQL Server.</span></span> <span data-ttu-id="b7b75-104">在使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，必须指定要连接到 SQL Server 生成的元数据的 URI。</span><span class="sxs-lookup"><span data-stu-id="b7b75-104">While using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you must specify the URI to connect to SQL Server to generate the metadata.</span></span> <span data-ttu-id="b7b75-105">虽然配置发送或接收端口使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你必须指定要连接到 SQL Server 以执行操作的 URI。</span><span class="sxs-lookup"><span data-stu-id="b7b75-105">While configuring a send or receive port using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you must specify the URI to connect to SQL Server to perform operations.</span></span>  
  
## <a name="enter-the-connection-uri-from-visual-studio"></a><span data-ttu-id="b7b75-106">从 Visual Studio 中输入连接 URI</span><span class="sxs-lookup"><span data-stu-id="b7b75-106">Enter the connection URI from Visual Studio</span></span>  
 <span data-ttu-id="b7b75-107">从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，你可以指定连接 URI 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b7b75-107">From [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you can specify the connection URI using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
### <a name="use-the-consume-adapter-service-add-in"></a><span data-ttu-id="b7b75-108">使用使用适配器服务外接程序</span><span class="sxs-lookup"><span data-stu-id="b7b75-108">Use the Consume Adapter Service Add-in</span></span>  
  
1.  <span data-ttu-id="b7b75-109">右键单击你的 BizTalk 项目，指向**添加**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="b7b75-109">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="b7b75-110">在**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b7b75-110">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="b7b75-111">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b7b75-111">Use this</span></span>|<span data-ttu-id="b7b75-112">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b7b75-112">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b7b75-113">**类别**</span><span class="sxs-lookup"><span data-stu-id="b7b75-113">**Categories**</span></span>|<span data-ttu-id="b7b75-114">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="b7b75-114">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="b7b75-115">**模板**</span><span class="sxs-lookup"><span data-stu-id="b7b75-115">**Templates**</span></span>|<span data-ttu-id="b7b75-116">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="b7b75-116">Click **Consume Adapter Service**.</span></span>|  
  
3.  <span data-ttu-id="b7b75-117">若要启动**使用适配器服务**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="b7b75-117">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="b7b75-118">在**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**sqlBinding**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="b7b75-118">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **sqlBinding**, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="b7b75-119">在**配置适配器**对话框中，单击**安全**选项卡。从**客户端凭据类型**列表中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="b7b75-119">In the **Configure Adapter** dialog box, click the **Security** tab. From the **Client credential type** list, do one of the following:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b7b75-120">中所述，如果你要连接到 SQL Server 使用 Windows 身份验证，必须到 SQL Server 中添加与你登录的 Windows 用户[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="b7b75-120">If you are connecting to SQL Server using Windows Authentication, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
    |<span data-ttu-id="b7b75-121">单击此链接</span><span class="sxs-lookup"><span data-stu-id="b7b75-121">Click this</span></span>|<span data-ttu-id="b7b75-122">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b7b75-122">To do this</span></span>|  
    |----------------|----------------|  
    |<span data-ttu-id="b7b75-123">**无**</span><span class="sxs-lookup"><span data-stu-id="b7b75-123">**None**</span></span>|<span data-ttu-id="b7b75-124">使用 Windows 身份验证连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b7b75-124">Connect to SQL Server by using Windows authentication.</span></span>|  
    |<span data-ttu-id="b7b75-125">**Windows**</span><span class="sxs-lookup"><span data-stu-id="b7b75-125">**Windows**</span></span>|<span data-ttu-id="b7b75-126">使用 Windows 身份验证连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b7b75-126">Connect to SQL Server by using Windows authentication.</span></span>|  
    |<span data-ttu-id="b7b75-127">**用户名**</span><span class="sxs-lookup"><span data-stu-id="b7b75-127">**Username**</span></span>|<span data-ttu-id="b7b75-128">通过指定 SQL Server 数据库中定义的用户凭据，指定用于连接 SQL Server 的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="b7b75-128">Specify the user name and password to connect to SQL Server by specifying credentials for a user defined in SQL Server database.</span></span> <span data-ttu-id="b7b75-129">请注意，用户名和密码区分大小写。</span><span class="sxs-lookup"><span data-stu-id="b7b75-129">Note that the user name and password are case-sensitive.</span></span> <span data-ttu-id="b7b75-130">**注意：** 如果你离开**用户名**和**密码**为空白字段，该适配器将连接到 SQL Server 使用 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7b75-130">**Note:**  If you leave the **User name** and **Password** fields as blank, the adapter connects to SQL Server using Windows authentication.</span></span>|  
  
6.  <span data-ttu-id="b7b75-131">单击**URI 属性**选项卡，然后指定不同的参数的值。</span><span class="sxs-lookup"><span data-stu-id="b7b75-131">Click the **URI Properties** tab, and specify values for different parameters.</span></span> <span data-ttu-id="b7b75-132">有关连接 URI 的详细信息为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="b7b75-132">For more information about the connection URI for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Create the SQL Server Connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  
  
7.  <span data-ttu-id="b7b75-133">单击**绑定属性**选项卡，然后指定绑定属性的值如果有的话，生成架构之前所需的。</span><span class="sxs-lookup"><span data-stu-id="b7b75-133">Click the **Binding Properties** tab, and specify values for the binding properties, if any, which are required before generating the schema.</span></span> <span data-ttu-id="b7b75-134">有关绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="b7b75-134">For more information about binding properties, see [Read about the BizTalk Adapter for SQL Server adapter Binding Properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
8.  <span data-ttu-id="b7b75-135">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="b7b75-135">Click **OK**.</span></span>  
  
### <a name="use-the-add-adapter-metadata-wizard"></a><span data-ttu-id="b7b75-136">使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="b7b75-136">Use the Add Adapter Metadata wizard</span></span>  
  
1.  <span data-ttu-id="b7b75-137">右键单击 BizTalk 项目，指向**添加**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="b7b75-137">Right-click the BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="b7b75-138">在**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b7b75-138">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="b7b75-139">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b7b75-139">Use this</span></span>|<span data-ttu-id="b7b75-140">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b7b75-140">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b7b75-141">**类别**</span><span class="sxs-lookup"><span data-stu-id="b7b75-141">**Categories**</span></span>|<span data-ttu-id="b7b75-142">单击**添加适配器**。</span><span class="sxs-lookup"><span data-stu-id="b7b75-142">Click **Add Adapter**.</span></span>|  
    |<span data-ttu-id="b7b75-143">**模板**</span><span class="sxs-lookup"><span data-stu-id="b7b75-143">**Templates**</span></span>|<span data-ttu-id="b7b75-144">单击**添加适配器元数据**。</span><span class="sxs-lookup"><span data-stu-id="b7b75-144">Click **Add Adapter Metadata**.</span></span>|  
  
3.  <span data-ttu-id="b7b75-145">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="b7b75-145">Click **Add**.</span></span> <span data-ttu-id="b7b75-146">此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。</span><span class="sxs-lookup"><span data-stu-id="b7b75-146">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  
  
4.  <span data-ttu-id="b7b75-147">在添加适配器向导中，选择**WCF SQL**。</span><span class="sxs-lookup"><span data-stu-id="b7b75-147">In the Add Adapter Wizard, select **WCF-SQL**.</span></span> <span data-ttu-id="b7b75-148">选择在其安装 BizTalk Server 的计算机和 BizTalk 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="b7b75-148">Select the computer on which BizTalk Server is installed and the name of the BizTalk database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="b7b75-149">如果你已经在 BizTalk 中配置 WCF SQL 端口，选择从端口**端口**列表。</span><span class="sxs-lookup"><span data-stu-id="b7b75-149">If you already have a WCF-SQL port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
5.  <span data-ttu-id="b7b75-150">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="b7b75-150">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="b7b75-151">在**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**sqlBinding**，然后单击**配置**.</span><span class="sxs-lookup"><span data-stu-id="b7b75-151">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list, select **sqlBinding**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="b7b75-152">在**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表框中，执行下列其中一项：</span><span class="sxs-lookup"><span data-stu-id="b7b75-152">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential  type** drop-down list box, do one of the following:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b7b75-153">中所述，如果你要连接到 SQL Server 使用 Windows 身份验证，必须到 SQL Server 中添加与你登录的 Windows 用户[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="b7b75-153">If you are connecting to SQL Server using Windows Authentication, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
    |<span data-ttu-id="b7b75-154">单击此链接</span><span class="sxs-lookup"><span data-stu-id="b7b75-154">Click this</span></span>|<span data-ttu-id="b7b75-155">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b7b75-155">To do this</span></span>|  
    |----------------|----------------|  
    |<span data-ttu-id="b7b75-156">**无**</span><span class="sxs-lookup"><span data-stu-id="b7b75-156">**None**</span></span>|<span data-ttu-id="b7b75-157">使用 Windows 身份验证连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b7b75-157">Connect to SQL Server by using Windows authentication.</span></span>|  
    |<span data-ttu-id="b7b75-158">**Windows**</span><span class="sxs-lookup"><span data-stu-id="b7b75-158">**Windows**</span></span>|<span data-ttu-id="b7b75-159">使用 Windows 身份验证连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b7b75-159">Connect to SQL Server by using Windows authentication.</span></span>|  
    |<span data-ttu-id="b7b75-160">**用户名**</span><span class="sxs-lookup"><span data-stu-id="b7b75-160">**Username**</span></span>|<span data-ttu-id="b7b75-161">通过指定 SQL Server 数据库中定义的用户凭据，指定用于连接 SQL Server 的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="b7b75-161">Specify the user name and password to connect to SQL Server by specifying credentials for a user defined in SQL Server database.</span></span> <span data-ttu-id="b7b75-162">请注意，用户名和密码区分大小写。</span><span class="sxs-lookup"><span data-stu-id="b7b75-162">Note that the user name and password are case-sensitive.</span></span> <span data-ttu-id="b7b75-163">**注意：** 如果你离开**用户名**和**密码**为空白字段，该适配器将连接到 SQL Server 使用 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7b75-163">**Note:**  If you leave the **User name** and **Password** fields as blank, the adapter connects to SQL Server using Windows authentication.</span></span>|  
  
8.  <span data-ttu-id="b7b75-164">单击**URI 属性**选项卡上，然后指定连接参数的值。</span><span class="sxs-lookup"><span data-stu-id="b7b75-164">Click the **URI Properties** tab, and then specify values for the connection parameters.</span></span> <span data-ttu-id="b7b75-165">有关连接 URI 的详细信息为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="b7b75-165">For more information about the connection URI for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Create the SQL Server Connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  
  
9. <span data-ttu-id="b7b75-166">单击**绑定属性**选项卡上，然后指定绑定属性的值，如果任何，所需的要设定为目标的操作。</span><span class="sxs-lookup"><span data-stu-id="b7b75-166">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="b7b75-167">有关绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="b7b75-167">For more information about binding properties, see [Read about the BizTalk Adapter for SQL Server adapter Binding Properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b7b75-168">如果你选择现有 WCF SQL 发送端口，你不需要指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="b7b75-168">If you selected an existing WCF-SQL send port, you need not specify the binding properties.</span></span> <span data-ttu-id="b7b75-169">绑定属性是从发送端口配置中选取。</span><span class="sxs-lookup"><span data-stu-id="b7b75-169">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="b7b75-170">但是，你可以选择指定所需在设计时，如果任何绑定属性。</span><span class="sxs-lookup"><span data-stu-id="b7b75-170">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="b7b75-171">在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。</span><span class="sxs-lookup"><span data-stu-id="b7b75-171">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="b7b75-172">但是，在运行时指定中发送端口配置的绑定属性的值将适用。</span><span class="sxs-lookup"><span data-stu-id="b7b75-172">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  
  
10. <span data-ttu-id="b7b75-173">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="b7b75-173">Click **OK**.</span></span>  
  
## <a name="enter-the-connection-uri-from-the-biztalk-server-administration-console"></a><span data-ttu-id="b7b75-174">从 BizTalk Server 管理控制台中输入连接 URI</span><span class="sxs-lookup"><span data-stu-id="b7b75-174">Enter the connection URI from the BizTalk Server Administration Console</span></span>  
 <span data-ttu-id="b7b75-175">从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你可以指定连接 URI 作为 WCF 自定义或 WCF SQL 端口配置的一部分。</span><span class="sxs-lookup"><span data-stu-id="b7b75-175">From the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can specify the connection URI as part of the WCF-Custom or a WCF-SQL port configuration.</span></span>  
  
### <a name="enter-the-connection-uri-for-the-wcf-custom-port"></a><span data-ttu-id="b7b75-176">输入 WCF 自定义端口的连接 URI</span><span class="sxs-lookup"><span data-stu-id="b7b75-176">Enter the connection URI for the WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="b7b75-177">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="b7b75-177">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="b7b75-178">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="b7b75-178">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="b7b75-179">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="b7b75-179">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="b7b75-180">在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="b7b75-180">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b7b75-181">若要查看接收端口的位置属性对话框中，单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="b7b75-181">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="b7b75-182">在**WCF 自定义传输属性**对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="b7b75-182">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
5.  <span data-ttu-id="b7b75-183">在**地址 (URI)** 文本框中，指定连接 URI 来连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b7b75-183">In the **Address (URI)** text box, specify the connection URI to connect to SQL Server.</span></span> <span data-ttu-id="b7b75-184">有关连接 URI 的详细信息为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="b7b75-184">For more information about the connection URI for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Create the SQL Server Connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  
  
6.  <span data-ttu-id="b7b75-185">在**WCF 自定义传输属性**对话框中，单击**绑定**选项卡。从**绑定类型**下拉列表中，选择**sqlBinding**。</span><span class="sxs-lookup"><span data-stu-id="b7b75-185">In the **WCF-Custom Transport Properties** dialog box, click the **Binding** tab. From the **Binding Type** drop-down list, select **sqlBinding**.</span></span>  
  
7.  <span data-ttu-id="b7b75-186">如果您创建发送端口，则在**WCF 自定义传输属性**对话框中，单击**凭据**选项卡，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="b7b75-186">If you are creating a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="b7b75-187">选择**不使用单一登录**选项，并指定用户名和密码以连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b7b75-187">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="b7b75-188">请注意，用户名和密码区分大小写。</span><span class="sxs-lookup"><span data-stu-id="b7b75-188">Note that the user name and password are case-sensitive.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="b7b75-189">如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空白的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="b7b75-189">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span> <span data-ttu-id="b7b75-190">中所述执行此操作之前，必须将与你登录 Windows 用户添加到 SQL Server[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="b7b75-190">Before you do this, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
    -   <span data-ttu-id="b7b75-191">选择**使用单一登录**选项，并指定分支机构的企业单一登录 (SSO) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b7b75-191">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
8.  <span data-ttu-id="b7b75-192">如果您创建接收端口，则在**WCF 自定义传输属性**对话框中，单击**其他**选项卡，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="b7b75-192">If you are creating a receive port, in the **WCF-Custom Transport Properties** dialog box, click the **Other** tab, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="b7b75-193">选择**用户帐户**选项，并指定用户名和密码以连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b7b75-193">Select **User account** option, and specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="b7b75-194">请注意，用户名和密码区分大小写。</span><span class="sxs-lookup"><span data-stu-id="b7b75-194">Note that the user name and password are case-sensitive.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="b7b75-195">如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空白的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="b7b75-195">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span> <span data-ttu-id="b7b75-196">中所述执行此操作之前，必须将与你登录 Windows 用户添加到 SQL Server[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="b7b75-196">Before you do this, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
    -   <span data-ttu-id="b7b75-197">选择**Get 凭据 affiliate 应用程序**选项，然后指定关联 SSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b7b75-197">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  
  
9. <span data-ttu-id="b7b75-198">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="b7b75-198">Click **OK**.</span></span>  
  
### <a name="enter-the-connection-uri-for-the-wcf-sql-port"></a><span data-ttu-id="b7b75-199">输入 WCF SQL 端口的连接 URI</span><span class="sxs-lookup"><span data-stu-id="b7b75-199">Enter the connection URI for the WCF-SQL port</span></span>  
  
1.  <span data-ttu-id="b7b75-200">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="b7b75-200">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="b7b75-201">添加到 WCF SQL 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="b7b75-201">Add the WCF-SQL adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="b7b75-202">有关说明，请参阅[将 SQL 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="b7b75-202">For instructions, see [Adding the SQL Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="b7b75-203">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="b7b75-203">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="b7b75-204">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="b7b75-204">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="b7b75-205">在端口属性对话框中，从**类型**下拉列表中，选择更早版本，添加了 WCF SQL 适配器，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="b7b75-205">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SQL adapter you added earlier, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b7b75-206">若要查看接收端口的位置属性对话框中，单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="b7b75-206">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
5.  <span data-ttu-id="b7b75-207">在传输属性对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="b7b75-207">In the transport properties dialog box, click the **General** tab.</span></span>  
  
6.  <span data-ttu-id="b7b75-208">单击**配置**按钮，然后提供的连接参数的值。</span><span class="sxs-lookup"><span data-stu-id="b7b75-208">Click the **Configure** button and provide values for the connection parameters.</span></span> <span data-ttu-id="b7b75-209">有关连接 URI 的详细信息为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="b7b75-209">For more information about the connection URI for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Create the SQL Server Connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  
  
7.  <span data-ttu-id="b7b75-210">在传输属性对话框中，单击**绑定**选项卡上，并指定绑定属性的值。</span><span class="sxs-lookup"><span data-stu-id="b7b75-210">In the transport properties dialog box, click the **Binding** tab and specify values for binding properties.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b7b75-211">绑定属性显示的配置发送端口或接收端口。</span><span class="sxs-lookup"><span data-stu-id="b7b75-211">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="b7b75-212">例如，与通知相关的绑定属性不可用时配置发送端口，因为通知是入站的操作，需要接收端口配置。</span><span class="sxs-lookup"><span data-stu-id="b7b75-212">For example, binding properties related to notifications are not available while configuring a send port because notifications are inbound operations and require a receive port configuration.</span></span>  
  
8.  <span data-ttu-id="b7b75-213">如果您创建发送端口，则在传输属性对话框中，单击**凭据**选项卡，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="b7b75-213">If you are creating a send port, in the transport properties dialog box, click the **Credentials** tab, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="b7b75-214">选择**不使用单一登录**选项，并指定用户名和密码以连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b7b75-214">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="b7b75-215">请注意，用户名和密码区分大小写。</span><span class="sxs-lookup"><span data-stu-id="b7b75-215">Note that the user name and password are case-sensitive.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="b7b75-216">如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空白的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="b7b75-216">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span> <span data-ttu-id="b7b75-217">中所述执行此操作之前，必须将与你登录 Windows 用户添加到 SQL Server[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="b7b75-217">Before you do this, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
    -   <span data-ttu-id="b7b75-218">选择**使用单一登录**选项，并指定分支机构的企业单一登录 (SSO) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b7b75-218">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
9. <span data-ttu-id="b7b75-219">如果您创建接收端口，则在传输属性对话框中，单击**其他**选项卡，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="b7b75-219">If you are creating a receive port, in the transport properties dialog box, click the **Other** tab, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="b7b75-220">选择**用户帐户**选项，并指定用户名和密码以连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b7b75-220">Select **User account** option, and specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="b7b75-221">请注意，用户名和密码区分大小写。</span><span class="sxs-lookup"><span data-stu-id="b7b75-221">Note that the user name and password are case-sensitive.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="b7b75-222">如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空白的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="b7b75-222">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span> <span data-ttu-id="b7b75-223">中所述执行此操作之前，必须将与你登录 Windows 用户添加到 SQL Server[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="b7b75-223">Before you do this, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
    -   <span data-ttu-id="b7b75-224">选择**Get 凭据 affiliate 应用程序**选项，然后指定关联 SSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b7b75-224">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  
  
10. <span data-ttu-id="b7b75-225">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="b7b75-225">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7b75-226">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7b75-226">See Also</span></span>  
[<span data-ttu-id="b7b75-227">开发具有 SQL 适配器的 BizTalk 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="b7b75-227">Building blocks to develop BizTalk applications with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)