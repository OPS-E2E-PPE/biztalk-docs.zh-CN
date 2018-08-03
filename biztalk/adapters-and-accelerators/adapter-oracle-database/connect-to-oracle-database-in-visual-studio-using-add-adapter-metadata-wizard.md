---
title: 连接到 Visual Studio 中使用添加适配器元数据向导中的 Oracle 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 726b3f82-887c-407a-bb9f-dcb9443155b0
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fe5ebb085055307730f65cd36fea29f68deeccf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996534"
---
# <a name="connect-to-oracle-database-in-visual-studio-using-add-adapter-metadata-wizard"></a><span data-ttu-id="09667-102">连接到 Oracle 数据库，在 Visual Studio 中使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="09667-102">Connect to Oracle Database in Visual Studio using Add Adapter Metadata Wizard</span></span>
<span data-ttu-id="09667-103">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]还会显示为 BizTalk 适配器，因此，您可以使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]来为你想要使用该适配器在 Oracle 数据库上执行的操作生成架构。</span><span class="sxs-lookup"><span data-stu-id="09667-103">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] is also exposed as a BizTalk adapter and, therefore, you can use the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] to generate schema for the operations you want to perform on the Oracle database using the adapter.</span></span>  

 <span data-ttu-id="09667-104">本主题说明了如何使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="09667-104">This topic provides instructions on how to use the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

## <a name="connecting-to-an-oracle-database-using-the-add-adapter-metadata-wizard"></a><span data-ttu-id="09667-105">连接到 Oracle 数据库使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="09667-105">Connecting to an Oracle Database Using the Add Adapter Metadata Wizard</span></span>  
 <span data-ttu-id="09667-106">执行以下步骤连接到 Oracle 数据库使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="09667-106">Perform the following steps to connect to an Oracle database using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

#### <a name="to-connect-to-an-oracle-database"></a><span data-ttu-id="09667-107">若要连接到 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="09667-107">To connect to an Oracle database</span></span>  

1. <span data-ttu-id="09667-108">若要使用连接[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]BizTalk 解决方案中：</span><span class="sxs-lookup"><span data-stu-id="09667-108">To connect using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] in a BizTalk solution:</span></span>  

   1. <span data-ttu-id="09667-109">右键单击解决方案资源管理器中的项目，指向**外**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="09667-109">Right-click the project in Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  

   2. <span data-ttu-id="09667-110">在中**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="09667-110">In the **Add Generated Items** dialog box, do the following:</span></span>  


      |    <span data-ttu-id="09667-111">使用此选项</span><span class="sxs-lookup"><span data-stu-id="09667-111">Use this</span></span>    |           <span data-ttu-id="09667-112">执行的操作</span><span class="sxs-lookup"><span data-stu-id="09667-112">To do this</span></span>            |
      |----------------|---------------------------------|
      | <span data-ttu-id="09667-113">**类别**</span><span class="sxs-lookup"><span data-stu-id="09667-113">**Categories**</span></span> |     <span data-ttu-id="09667-114">单击**将适配器添加**。</span><span class="sxs-lookup"><span data-stu-id="09667-114">Click **Add Adapter**.</span></span>      |
      | <span data-ttu-id="09667-115">**模板**</span><span class="sxs-lookup"><span data-stu-id="09667-115">**Templates**</span></span>  | <span data-ttu-id="09667-116">单击**添加适配器元数据**。</span><span class="sxs-lookup"><span data-stu-id="09667-116">Click **Add Adapter Metadata**.</span></span> |


   3. <span data-ttu-id="09667-117">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="09667-117">Click **Add**.</span></span> <span data-ttu-id="09667-118">此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。</span><span class="sxs-lookup"><span data-stu-id="09667-118">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  

   4. <span data-ttu-id="09667-119">在添加适配器元数据向导中，选择**Wcf-oracledb**。</span><span class="sxs-lookup"><span data-stu-id="09667-119">In the Add Adapter Metadata Wizard, select **WCF-OracleDB**.</span></span> <span data-ttu-id="09667-120">选择在其安装 BizTalk Server 的计算机和 BizTalk 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="09667-120">Select the computer on which BizTalk Server is installed and the name of the BizTalk database.</span></span>  

      > [!IMPORTANT]
      >  <span data-ttu-id="09667-121">如果已在 BizTalk 中配置的 Wcf-oracledb 端口，选择从端口**端口**列表。</span><span class="sxs-lookup"><span data-stu-id="09667-121">If you already have a WCF-OracleDB port configured in BizTalk, select the port from the **Port** list.</span></span>  

   5. <span data-ttu-id="09667-122">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="09667-122">Click **Next**.</span></span>  

2. <span data-ttu-id="09667-123">从**选择绑定**下拉列表中，选择**oracleDBBinding**然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="09667-123">From the **Select a binding** drop-down list, select **oracleDBBinding** and click **Configure**.</span></span>  

3. <span data-ttu-id="09667-124">在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表框中，选择**用户名**并指定用户名和密码以连接到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="09667-124">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Oracle database.</span></span>  

   1. <span data-ttu-id="09667-125">若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**并**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="09667-125">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span> <span data-ttu-id="09667-126">请确保指定的用户名和密码以连接到 Oracle 数据库时遵循以下注意事项：</span><span class="sxs-lookup"><span data-stu-id="09667-126">Make sure you adhere to the following considerations when specifying the user name and password to connect to an Oracle database:</span></span>  

      - <span data-ttu-id="09667-127">**用户名称**。</span><span class="sxs-lookup"><span data-stu-id="09667-127">**User name**.</span></span> <span data-ttu-id="09667-128">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将保留在打开对 Oracle 数据库的连接时输入的用户名的值的大小写。</span><span class="sxs-lookup"><span data-stu-id="09667-128">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] preserves the case of the value that you enter for the user name when it opens a connection on the Oracle database.</span></span> <span data-ttu-id="09667-129">对 Oracle 数据库用户名称是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="09667-129">User names on the Oracle database are case-sensitive.</span></span> <span data-ttu-id="09667-130">应确保提供 Oracle 用户名称[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]在所需的 Oracle 数据库的情况下。</span><span class="sxs-lookup"><span data-stu-id="09667-130">You should ensure that you provide Oracle user names to the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] in the case expected by your Oracle database.</span></span> <span data-ttu-id="09667-131">通常情况下，这意味着在 SCOTT/TIGER 凭据的用户名称应为大写:"SCOTT"。</span><span class="sxs-lookup"><span data-stu-id="09667-131">Typically, this means that the user name in the SCOTT/TIGER credential should be upper case: "SCOTT".</span></span>  

      - <span data-ttu-id="09667-132">**密码**。</span><span class="sxs-lookup"><span data-stu-id="09667-132">**Password**.</span></span> <span data-ttu-id="09667-133">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将保留在打开对 Oracle 数据库的连接时输入的密码值的大小写。</span><span class="sxs-lookup"><span data-stu-id="09667-133">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] preserves the case of the value that you enter for the password when it opens a connection on the Oracle database.</span></span> <span data-ttu-id="09667-134">对于发行版 10g 和更早版本，不区分大小写上 Oracle 系统的密码。</span><span class="sxs-lookup"><span data-stu-id="09667-134">For release 10g and earlier, passwords on the Oracle system are not case-sensitive.</span></span>  

   2. <span data-ttu-id="09667-135">若要使用 Windows 身份验证进行连接，请键入**/** 中**用户名**文本框中，保留**密码**文本框保留为空。</span><span class="sxs-lookup"><span data-stu-id="09667-135">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  

4. <span data-ttu-id="09667-136">单击**URI 属性**选项卡，并指定连接参数的值。</span><span class="sxs-lookup"><span data-stu-id="09667-136">Click the **URI Properties** tab, and specify values for the connection parameters.</span></span> <span data-ttu-id="09667-137">有关详细信息的连接 URI 对于[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[创建的 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="09667-137">For more information about the connection URI for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  

5. <span data-ttu-id="09667-138">单击**绑定属性**选项卡，然后指定绑定属性的值，如果你想要针对的操作，任何需要。</span><span class="sxs-lookup"><span data-stu-id="09667-138">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="09667-139">例如，如果你想要面向 POLLINGSTMT 操作，则必须设置**PollingStatement**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="09667-139">For example, if you want to target the POLLINGSTMT operation, you must set the **PollingStatement** binding property.</span></span> <span data-ttu-id="09667-140">有关绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="09667-140">For more information about binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>

   > [!NOTE]
   >  <span data-ttu-id="09667-141">如果您正在生成元数据中使用添加适配器元数据向导并选择现有 Wcf-oracledb 发送端口，则需要指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="09667-141">If you are generating metadata using Add Adapter Metadata Wizard and you selected an existing WCF-OracleDB send port, you need not specify the binding properties.</span></span> <span data-ttu-id="09667-142">绑定属性是从发送端口配置中选取。</span><span class="sxs-lookup"><span data-stu-id="09667-142">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="09667-143">但是，您可以选择指定如果任何，则需要在设计时的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="09667-143">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="09667-144">在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。</span><span class="sxs-lookup"><span data-stu-id="09667-144">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="09667-145">但是，在运行时指定的发送端口配置中的绑定属性的值将适用。</span><span class="sxs-lookup"><span data-stu-id="09667-145">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  

6. <span data-ttu-id="09667-146">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="09667-146">Click **OK**.</span></span>  

7. <span data-ttu-id="09667-147">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="09667-147">Click **Connect**.</span></span> <span data-ttu-id="09667-148">建立连接后，连接状态显示为**已连接**。</span><span class="sxs-lookup"><span data-stu-id="09667-148">After the connection is established, the connection status is shown as **Connected**.</span></span>  

    <span data-ttu-id="09667-149">下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。</span><span class="sxs-lookup"><span data-stu-id="09667-149">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span>  

    <span data-ttu-id="09667-150">![使用适配器服务连接对话框](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")</span><span class="sxs-lookup"><span data-stu-id="09667-150">![Consume Adapter Service dialog box connected](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")</span></span>  

## <a name="see-also"></a><span data-ttu-id="09667-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="09667-151">See Also</span></span>  
 <span data-ttu-id="09667-152">[连接到 Oracle 数据库，在 Visual Studio 中使用添加适配器服务引用](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-db-in-visual-studio-using-the-add-adapter-service.md) </span><span class="sxs-lookup"><span data-stu-id="09667-152">[Connect to the Oracle Database in Visual Studio using the Add Adapter Service Reference](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-db-in-visual-studio-using-the-add-adapter-service.md) </span></span>  
 [<span data-ttu-id="09667-153">连接到 Oracle 数据库使用 Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="09667-153">Connect to the Oracle Database Using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)