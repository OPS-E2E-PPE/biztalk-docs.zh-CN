---
title: 将连接到 Visual Studio 使用添加适配器元数据向导中的 Oracle E-business Suite |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4fadc722-0098-457e-a2e2-3e9cc96eab5e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5950b9ea6a0f5fc9856720202059cf1fd058a251
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216205"
---
# <a name="connect-to-oracle-e-business-suite-in-visual-studio-using-add-adapter-metadata-wizard"></a><span data-ttu-id="0e90d-102">将连接到 Visual Studio 使用添加适配器元数据向导中的 Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="0e90d-102">Connect to Oracle E-Business Suite in Visual Studio using Add Adapter Metadata Wizard</span></span>
<span data-ttu-id="0e90d-103">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]名称还公开为 BizTalk 适配器，因此，你可以使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]若要为你想要对 Oracle E-business Suite 使用适配器执行的操作生成架构。</span><span class="sxs-lookup"><span data-stu-id="0e90d-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is also exposed as a BizTalk adapter and, therefore, you can use the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] to generate schema for the operations you want to perform on Oracle E-Business Suite using the adapter.</span></span>  
  
## <a name="connecting-to-oracle-e-business-suite-using-the-add-adapter-metadata-wizard"></a><span data-ttu-id="0e90d-104">连接到 Oracle E-business Suite 使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="0e90d-104">Connecting to Oracle E-Business Suite Using the Add Adapter Metadata Wizard</span></span>  
 <span data-ttu-id="0e90d-105">执行以下步骤以连接到 Oracle E-business Suite 使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0e90d-105">Perform the following steps to connect to Oracle E-Business Suite using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
#### <a name="to-connect-to-oracle-e-business-suite"></a><span data-ttu-id="0e90d-106">以连接到 Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="0e90d-106">To connect to Oracle E-Business Suite</span></span>  
  
1.  <span data-ttu-id="0e90d-107">若要使用连接[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]BizTalk 解决方案中：</span><span class="sxs-lookup"><span data-stu-id="0e90d-107">To connect using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] in a BizTalk solution:</span></span>  
  
    1.  <span data-ttu-id="0e90d-108">创建 BizTalk 项目使用 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="0e90d-108">Create a BizTalk project using Visual Studio.</span></span>  
  
    2.  <span data-ttu-id="0e90d-109">右键单击解决方案资源管理器中的项目，指向**添加**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="0e90d-109">Right-click the project in Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
    3.  <span data-ttu-id="0e90d-110">在**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0e90d-110">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
        |<span data-ttu-id="0e90d-111">使用此选项</span><span class="sxs-lookup"><span data-stu-id="0e90d-111">Use this</span></span>|<span data-ttu-id="0e90d-112">执行的操作</span><span class="sxs-lookup"><span data-stu-id="0e90d-112">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="0e90d-113">**类别**</span><span class="sxs-lookup"><span data-stu-id="0e90d-113">**Categories**</span></span>|<span data-ttu-id="0e90d-114">单击**添加适配器**。</span><span class="sxs-lookup"><span data-stu-id="0e90d-114">Click **Add Adapter**.</span></span>|  
        |<span data-ttu-id="0e90d-115">**模板**</span><span class="sxs-lookup"><span data-stu-id="0e90d-115">**Templates**</span></span>|<span data-ttu-id="0e90d-116">单击**添加适配器元数据**。</span><span class="sxs-lookup"><span data-stu-id="0e90d-116">Click **Add Adapter Metadata**.</span></span>|  
  
    4.  <span data-ttu-id="0e90d-117">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="0e90d-117">Click **Add**.</span></span> <span data-ttu-id="0e90d-118">此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。</span><span class="sxs-lookup"><span data-stu-id="0e90d-118">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  
  
    5.  <span data-ttu-id="0e90d-119">在[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，选择**WCF OracleEBS**。</span><span class="sxs-lookup"><span data-stu-id="0e90d-119">In the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], select **WCF-OracleEBS**.</span></span> <span data-ttu-id="0e90d-120">选择的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装和 BizTalk 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="0e90d-120">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="0e90d-121">如果你已经在 BizTalk 中配置 WCF OracleEBS 端口，选择从端口**端口**列表。</span><span class="sxs-lookup"><span data-stu-id="0e90d-121">If you already have a WCF-OracleEBS port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
    6.  <span data-ttu-id="0e90d-122">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="0e90d-122">Click **Next**.</span></span>  
  
2.  <span data-ttu-id="0e90d-123">从**选择的绑定**下拉列表中，选择**oracleEBSBinding**单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="0e90d-123">From the **Select a binding** drop-down list, select **oracleEBSBinding** and click **Configure**.</span></span>  
  
3.  <span data-ttu-id="0e90d-124">在**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表框中，选择**用户名**和指定的用户名和密码以连接到 Oracle E-business Suite。</span><span class="sxs-lookup"><span data-stu-id="0e90d-124">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Oracle E-Business Suite.</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="0e90d-125">使用此选项</span><span class="sxs-lookup"><span data-stu-id="0e90d-125">Use this</span></span>|<span data-ttu-id="0e90d-126">执行的操作</span><span class="sxs-lookup"><span data-stu-id="0e90d-126">To do this</span></span>|  
    |<span data-ttu-id="0e90d-127">**使用 Oracle 数据库凭据进行连接**</span><span class="sxs-lookup"><span data-stu-id="0e90d-127">**To connect using Oracle database credentials**</span></span>|<span data-ttu-id="0e90d-128">指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="0e90d-128">Specify the **ClientCredentialType** binding property to **Database** and specify database credentials for **User name** and **Password** text boxes.</span></span>|  
    |<span data-ttu-id="0e90d-129">**若要使用 Oracle E-business Suite 凭据进行连接**</span><span class="sxs-lookup"><span data-stu-id="0e90d-129">**To connect using Oracle E-Business Suite credentials**</span></span>|<span data-ttu-id="0e90d-130">指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="0e90d-130">Specify the **ClientCredentialType** binding property to **EBusiness** and specify Oracle E-Business Suite credentials for **User name** and **Password** text boxes.</span></span> <span data-ttu-id="0e90d-131">在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**和**OraclePassword**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="0e90d-131">In this case, you must also specify Oracle database credentials for **OracleUserName** and **OraclePassword** binding properties.</span></span>|  
    |<span data-ttu-id="0e90d-132">**如果 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**</span><span class="sxs-lookup"><span data-stu-id="0e90d-132">**To connect using Windows Authentication if ClientCredentialType is set to “Database”**</span></span>|<span data-ttu-id="0e90d-133">指定的"/"为**用户名**文本框和离开**密码**文本框保留为空白。</span><span class="sxs-lookup"><span data-stu-id="0e90d-133">Specify a “/” for the **User name** text box and leave the **Password** text box blank.</span></span>|  
    |<span data-ttu-id="0e90d-134">**如果 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接**</span><span class="sxs-lookup"><span data-stu-id="0e90d-134">**To connect using Windows Authentication if ClientCredentialType is set to “EBusiness”**</span></span>|<span data-ttu-id="0e90d-135">指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="0e90d-135">Specify Oracle E-Business Suite credentials for **User name** and **Password** text boxes.</span></span> <span data-ttu-id="0e90d-136">你还必须指定"/"为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。</span><span class="sxs-lookup"><span data-stu-id="0e90d-136">You must also specify a “/” for the **OracleUserName** binding property and leave the **OraclePassword** binding property blank.</span></span>|  
  
4.  <span data-ttu-id="0e90d-137">单击**URI 属性**选项卡，然后指定连接参数的值。</span><span class="sxs-lookup"><span data-stu-id="0e90d-137">Click the **URI Properties** tab, and specify values for the connection parameters.</span></span> <span data-ttu-id="0e90d-138">有关连接 URI 的详细信息为[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[创建 Oracle E-business Suite 连接 URI](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md))。</span><span class="sxs-lookup"><span data-stu-id="0e90d-138">For more information about the connection URI for the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], see [Create the Oracle E-Business Suite connection URI](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0e90d-139">如果连接参数包含任何保留的字符，则必须指定它们作为-处于**URI 属性**选项卡上，即，而无需使用任何转义字符。</span><span class="sxs-lookup"><span data-stu-id="0e90d-139">If the connection parameters contain any reserved characters, you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="0e90d-140">但是，如果你指定直接在 URI**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用适当的转义字符。</span><span class="sxs-lookup"><span data-stu-id="0e90d-140">However, if you specify the URI directly in the **Configure a URI** field and the connection parameters contain reserved characters, you must specify the connection parameters using proper escape characters.</span></span>  
  
5.  <span data-ttu-id="0e90d-141">单击**绑定属性**选项卡上，然后指定绑定属性的值，如果任何，所需的要设定为目标的操作。</span><span class="sxs-lookup"><span data-stu-id="0e90d-141">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="0e90d-142">有关绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="0e90d-142">For more information about binding properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0e90d-143">如果正在生成元数据中使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]并且选择现有 WCF OracleEBS 发送端口，你不需要指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="0e90d-143">If you are generating metadata using [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] and you selected an existing WCF-OracleEBS send port, you need not specify the binding properties.</span></span> <span data-ttu-id="0e90d-144">绑定属性是从发送端口配置中选取。</span><span class="sxs-lookup"><span data-stu-id="0e90d-144">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="0e90d-145">但是，你可以选择指定所需在设计时，如果任何绑定属性。</span><span class="sxs-lookup"><span data-stu-id="0e90d-145">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="0e90d-146">在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。</span><span class="sxs-lookup"><span data-stu-id="0e90d-146">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="0e90d-147">但是，在运行时指定中发送端口配置的绑定属性的值将适用。</span><span class="sxs-lookup"><span data-stu-id="0e90d-147">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  
  
6.  <span data-ttu-id="0e90d-148">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="0e90d-148">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="0e90d-149">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="0e90d-149">Click **Connect**.</span></span> <span data-ttu-id="0e90d-150">建立连接后，连接状态将显示为**已连接**。</span><span class="sxs-lookup"><span data-stu-id="0e90d-150">After the connection is established, the connection status is shown as **Connected**.</span></span>  
  
     <span data-ttu-id="0e90d-151">下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。</span><span class="sxs-lookup"><span data-stu-id="0e90d-151">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span>  
  
     <span data-ttu-id="0e90d-152">![使用适配器服务对话框](../../adapters-and-accelerators/adapter-oracle-ebs/media/6a2b21ed-0fd2-4874-a6a6-e59a467533f8.gif "6a2b21ed-0fd2-4874-a6a6-e59a467533f8")</span><span class="sxs-lookup"><span data-stu-id="0e90d-152">![Consume Adapter Service dialog box](../../adapters-and-accelerators/adapter-oracle-ebs/media/6a2b21ed-0fd2-4874-a6a6-e59a467533f8.gif "6a2b21ed-0fd2-4874-a6a6-e59a467533f8")</span></span>  
  
     <span data-ttu-id="0e90d-153">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]显示包含可以在 Oracle E-business Suite 和 Oracle 数据库执行的各种操作的不同节点。</span><span class="sxs-lookup"><span data-stu-id="0e90d-153">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] displays different nodes containing various operations that can be performed on the Oracle E-Business Suite and the Oracle database.</span></span> <span data-ttu-id="0e90d-154">在各种节点下的元数据的分类方式的详细信息，请参阅[连接到 Visual Studio 使用添加适配器元数据向导中的 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-ebs-in-visual-studio-using-add-adapter-metadata-wizard.md)。</span><span class="sxs-lookup"><span data-stu-id="0e90d-154">For more information on how the metadata is categorized under the various nodes, see [Connect to Oracle E-Business Suite in Visual Studio using Add Adapter Metadata Wizard](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-ebs-in-visual-studio-using-add-adapter-metadata-wizard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e90d-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e90d-155">See Also</span></span>  
 <span data-ttu-id="0e90d-156">[将连接到 Oracle E-business Suite Visual Studio 中](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="0e90d-156">[Connect to the Oracle E-Business Suite in Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md) </span></span>  
 [<span data-ttu-id="0e90d-157">将连接到 Oracle E-business Suite 使用 Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="0e90d-157">Connect to Oracle E-Business Suite using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)