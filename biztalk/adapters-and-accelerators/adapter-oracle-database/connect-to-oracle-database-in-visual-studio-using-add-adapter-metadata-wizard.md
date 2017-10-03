---
title: "连接到 Visual Studio 使用添加适配器元数据向导中的 Oracle 数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 726b3f82-887c-407a-bb9f-dcb9443155b0
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbf023a306e7caabeb3e207f90831167f46e8009
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-oracle-database-in-visual-studio-using-add-adapter-metadata-wizard"></a><span data-ttu-id="9c2a6-102">连接到 Oracle 数据库在 Visual Studio 中使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="9c2a6-102">Connect to Oracle Database in Visual Studio using Add Adapter Metadata Wizard</span></span>
<span data-ttu-id="9c2a6-103">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]名称还公开为 BizTalk 适配器，因此，你可以使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]若要为你想要使用该适配器对 Oracle 数据库执行的操作生成架构。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-103">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] is also exposed as a BizTalk adapter and, therefore, you can use the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] to generate schema for the operations you want to perform on the Oracle database using the adapter.</span></span>  
  
 <span data-ttu-id="9c2a6-104">本主题将说明了如何使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-104">This topic provides instructions on how to use the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
## <a name="connecting-to-an-oracle-database-using-the-add-adapter-metadata-wizard"></a><span data-ttu-id="9c2a6-105">连接到 Oracle 数据库使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="9c2a6-105">Connecting to an Oracle Database Using the Add Adapter Metadata Wizard</span></span>  
 <span data-ttu-id="9c2a6-106">执行以下步骤以连接到 Oracle 数据库使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-106">Perform the following steps to connect to an Oracle database using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
#### <a name="to-connect-to-an-oracle-database"></a><span data-ttu-id="9c2a6-107">若要连接到 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="9c2a6-107">To connect to an Oracle database</span></span>  
  
1.  <span data-ttu-id="9c2a6-108">若要使用连接[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]BizTalk 解决方案中：</span><span class="sxs-lookup"><span data-stu-id="9c2a6-108">To connect using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] in a BizTalk solution:</span></span>  
  
    1.  <span data-ttu-id="9c2a6-109">右键单击解决方案资源管理器中的项目，指向**添加**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-109">Right-click the project in Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
    2.  <span data-ttu-id="9c2a6-110">在**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9c2a6-110">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
        |<span data-ttu-id="9c2a6-111">使用此选项</span><span class="sxs-lookup"><span data-stu-id="9c2a6-111">Use this</span></span>|<span data-ttu-id="9c2a6-112">执行的操作</span><span class="sxs-lookup"><span data-stu-id="9c2a6-112">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="9c2a6-113">**类别**</span><span class="sxs-lookup"><span data-stu-id="9c2a6-113">**Categories**</span></span>|<span data-ttu-id="9c2a6-114">单击**添加适配器**。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-114">Click **Add Adapter**.</span></span>|  
        |<span data-ttu-id="9c2a6-115">**模板**</span><span class="sxs-lookup"><span data-stu-id="9c2a6-115">**Templates**</span></span>|<span data-ttu-id="9c2a6-116">单击**添加适配器元数据**。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-116">Click **Add Adapter Metadata**.</span></span>|  
  
    3.  <span data-ttu-id="9c2a6-117">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-117">Click **Add**.</span></span> <span data-ttu-id="9c2a6-118">此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-118">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  
  
    4.  <span data-ttu-id="9c2a6-119">在添加适配器元数据向导中，选择**WCF OracleDB**。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-119">In the Add Adapter Metadata Wizard, select **WCF-OracleDB**.</span></span> <span data-ttu-id="9c2a6-120">选择在其安装 BizTalk Server 的计算机和 BizTalk 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-120">Select the computer on which BizTalk Server is installed and the name of the BizTalk database.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="9c2a6-121">如果你已经在 BizTalk 中配置 WCF OracleDB 端口，选择从端口**端口**列表。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-121">If you already have a WCF-OracleDB port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
    5.  <span data-ttu-id="9c2a6-122">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-122">Click **Next**.</span></span>  
  
2.  <span data-ttu-id="9c2a6-123">从**选择的绑定**下拉列表中，选择**oracleDBBinding**单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-123">From the **Select a binding** drop-down list, select **oracleDBBinding** and click **Configure**.</span></span>  
  
3.  <span data-ttu-id="9c2a6-124">在**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表框中，选择**用户名**和指定的用户名和密码以连接到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-124">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Oracle database.</span></span>  
  
    1.  <span data-ttu-id="9c2a6-125">若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-125">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span> <span data-ttu-id="9c2a6-126">请确保指定的用户名和密码以连接到 Oracle 数据库时遵循以下注意事项：</span><span class="sxs-lookup"><span data-stu-id="9c2a6-126">Make sure you adhere to the following considerations when specifying the user name and password to connect to an Oracle database:</span></span>  
  
        -   <span data-ttu-id="9c2a6-127">**用户名称**。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-127">**User name**.</span></span> <span data-ttu-id="9c2a6-128">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]保留在打开对 Oracle 数据库的连接时输入的用户名的值的大小写。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-128">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] preserves the case of the value that you enter for the user name when it opens a connection on the Oracle database.</span></span> <span data-ttu-id="9c2a6-129">对 Oracle 数据库的用户名称是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-129">User names on the Oracle database are case-sensitive.</span></span> <span data-ttu-id="9c2a6-130">您应该确保你提供到的 Oracle 用户名[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]在 Oracle 数据库所需的情况下。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-130">You should ensure that you provide Oracle user names to the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] in the case expected by your Oracle database.</span></span> <span data-ttu-id="9c2a6-131">通常，这意味着在 SCOTT/TIGER 凭据的用户名称应为大写形式:"SCOTT"。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-131">Typically, this means that the user name in the SCOTT/TIGER credential should be upper case: "SCOTT".</span></span>  
  
        -   <span data-ttu-id="9c2a6-132">**密码**。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-132">**Password**.</span></span> <span data-ttu-id="9c2a6-133">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]保留在打开对 Oracle 数据库的连接时输入的密码的值的大小写。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-133">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] preserves the case of the value that you enter for the password when it opens a connection on the Oracle database.</span></span> <span data-ttu-id="9c2a6-134">对于发行版 10g 和更早版本，Oracle 系统上的密码是不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-134">For release 10g and earlier, passwords on the Oracle system are not case-sensitive.</span></span>  
  
    2.  <span data-ttu-id="9c2a6-135">若要使用 Windows 身份验证进行连接，请键入 **/** 中**用户名**文本框和离开**密码**文本框保留为空白。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-135">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
4.  <span data-ttu-id="9c2a6-136">单击**URI 属性**选项卡，然后指定连接参数的值。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-136">Click the **URI Properties** tab, and specify values for the connection parameters.</span></span> <span data-ttu-id="9c2a6-137">有关连接 URI 的详细信息为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[创建 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-137">For more information about the connection URI for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  
  
5.  <span data-ttu-id="9c2a6-138">单击**绑定属性**选项卡上，然后指定绑定属性的值，如果任何，所需的要设定为目标的操作。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-138">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="9c2a6-139">例如，如果你想要针对 POLLINGSTMT 操作，则必须设置**PollingStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-139">For example, if you want to target the POLLINGSTMT operation, you must set the **PollingStatement** binding property.</span></span> <span data-ttu-id="9c2a6-140">有关绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-140">For more information about binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="9c2a6-141">如果您正在生成元数据中使用添加适配器元数据向导并且你选择现有的 WCF OracleDB 发送端口，你需要指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-141">If you are generating metadata using Add Adapter Metadata Wizard and you selected an existing WCF-OracleDB send port, you need not specify the binding properties.</span></span> <span data-ttu-id="9c2a6-142">绑定属性是从发送端口配置中选取。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-142">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="9c2a6-143">但是，你可以选择指定所需在设计时，如果任何绑定属性。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-143">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="9c2a6-144">在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-144">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="9c2a6-145">但是，在运行时指定中发送端口配置的绑定属性的值将适用。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-145">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  
  
6.  <span data-ttu-id="9c2a6-146">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-146">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="9c2a6-147">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-147">Click **Connect**.</span></span> <span data-ttu-id="9c2a6-148">建立连接后，连接状态将显示为**已连接**。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-148">After the connection is established, the connection status is shown as **Connected**.</span></span>  
  
     <span data-ttu-id="9c2a6-149">下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。</span><span class="sxs-lookup"><span data-stu-id="9c2a6-149">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span>  
  
     <span data-ttu-id="9c2a6-150">![使用适配器服务连接的对话框](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")</span><span class="sxs-lookup"><span data-stu-id="9c2a6-150">![Consume Adapter Service dialog box connected](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c2a6-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c2a6-151">See Also</span></span>  
 <span data-ttu-id="9c2a6-152">[连接到 Oracle 数据库在 Visual Studio 中使用添加适配器服务引用](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-db-in-visual-studio-using-the-add-adapter-service.md) </span><span class="sxs-lookup"><span data-stu-id="9c2a6-152">[Connect to the Oracle Database in Visual Studio using the Add Adapter Service Reference](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-db-in-visual-studio-using-the-add-adapter-service.md) </span></span>  
 [<span data-ttu-id="9c2a6-153">连接到 Oracle 数据库使用 Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="9c2a6-153">Connect to the Oracle Database Using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)