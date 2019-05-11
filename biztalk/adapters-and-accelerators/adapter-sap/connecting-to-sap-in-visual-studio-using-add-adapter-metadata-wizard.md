---
title: Visual Studio 中使用连接到 SAP 添加适配器元数据向导 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a442837b-e7d8-4edb-9c5e-5603d4c58fe5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd2c7eecc6bf7edaaf51faea7962bd8a32785caf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373609"
---
# <a name="connecting-to-sap-in-visual-studio-using-add-adapter-metadata-wizard"></a><span data-ttu-id="7b64b-102">Visual Studio 中使用连接到 SAP 添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="7b64b-102">Connecting to SAP in Visual Studio Using Add Adapter Metadata Wizard</span></span>
<span data-ttu-id="7b64b-103">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]还会显示为 BizTalk 适配器，因此，可以使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]来为你想要在使用适配器的 SAP 系统上执行的操作生成架构。</span><span class="sxs-lookup"><span data-stu-id="7b64b-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is also exposed as a BizTalk adapter and hence, you can use the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] to generate schema for the operations you want to perform on an SAP system using the adapter.</span></span>  

## <a name="connecting-to-an-sap-system-using-add-adapter-metadata-wizard"></a><span data-ttu-id="7b64b-104">连接到 SAP 系统使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="7b64b-104">Connecting to an SAP System Using Add Adapter Metadata Wizard</span></span>  
 <span data-ttu-id="7b64b-105">执行以下步骤连接到 SAP 系统使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7b64b-105">Perform the following steps to connect to an SAP system using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

#### <a name="to-connect-to-an-sap-system"></a><span data-ttu-id="7b64b-106">若要连接到 SAP 系统</span><span class="sxs-lookup"><span data-stu-id="7b64b-106">To connect to an SAP system</span></span>  

1. <span data-ttu-id="7b64b-107">若要使用连接[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]BizTalk 解决方案中：</span><span class="sxs-lookup"><span data-stu-id="7b64b-107">To connect using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] in a BizTalk solution:</span></span>  

   1. <span data-ttu-id="7b64b-108">创建 BizTalk 项目使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7b64b-108">Create a BizTalk project using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  

   2. <span data-ttu-id="7b64b-109">右键单击解决方案资源管理器中的项目名称，指向**外**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="7b64b-109">Right-click the project name in Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  

   3. <span data-ttu-id="7b64b-110">在中**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7b64b-110">In the **Add Generated Items** dialog box, do the following:</span></span>  


      |    <span data-ttu-id="7b64b-111">使用此选项</span><span class="sxs-lookup"><span data-stu-id="7b64b-111">Use this</span></span>    |           <span data-ttu-id="7b64b-112">执行的操作</span><span class="sxs-lookup"><span data-stu-id="7b64b-112">To do this</span></span>            |
      |----------------|---------------------------------|
      | <span data-ttu-id="7b64b-113">**类别**</span><span class="sxs-lookup"><span data-stu-id="7b64b-113">**Categories**</span></span> |     <span data-ttu-id="7b64b-114">单击**将适配器添加**。</span><span class="sxs-lookup"><span data-stu-id="7b64b-114">Click **Add Adapter**.</span></span>      |
      | <span data-ttu-id="7b64b-115">**模板**</span><span class="sxs-lookup"><span data-stu-id="7b64b-115">**Templates**</span></span>  | <span data-ttu-id="7b64b-116">单击**添加适配器元数据**。</span><span class="sxs-lookup"><span data-stu-id="7b64b-116">Click **Add Adapter Metadata**.</span></span> |


   4. <span data-ttu-id="7b64b-117">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="7b64b-117">Click **Add**.</span></span> <span data-ttu-id="7b64b-118">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]随即打开。</span><span class="sxs-lookup"><span data-stu-id="7b64b-118">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  

   5. <span data-ttu-id="7b64b-119">在添加适配器向导中，选择**WCF-SAP**。</span><span class="sxs-lookup"><span data-stu-id="7b64b-119">In the Add Adapter Wizard, select **WCF-SAP**.</span></span> <span data-ttu-id="7b64b-120">选择的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装和 BizTalk 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="7b64b-120">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  

      > [!IMPORTANT]
      >  <span data-ttu-id="7b64b-121">如果已配置 BizTalk 中的 WCF SAP 端口，选择从端口**端口**列表。</span><span class="sxs-lookup"><span data-stu-id="7b64b-121">If you already have a WCF-SAP port configured in BizTalk, select the port from the **Port** list.</span></span>  

   6. <span data-ttu-id="7b64b-122">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="7b64b-122">Click **Next**.</span></span>  

2. <span data-ttu-id="7b64b-123">从**选择绑定**下拉列表中，选择**sapBinding**然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="7b64b-123">From the **Select a binding** drop-down list, select **sapBinding** and click **Configure**.</span></span>  

3. <span data-ttu-id="7b64b-124">在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表框中，选择**用户名**并指定用户名和密码以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="7b64b-124">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the SAP system.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="7b64b-125">如果使用 SAP 安全网络连接 (SNC) 库来连接到 SAP 系统，则不指定用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="7b64b-125">If you are using the SAP Secure Network Connection (SNC) library to connect to an SAP system, do not specify a username and password.</span></span>  

4. <span data-ttu-id="7b64b-126">单击**URI 属性**选项卡，指定连接参数的值。</span><span class="sxs-lookup"><span data-stu-id="7b64b-126">Click the **URI Properties** tab and specify values for the connection parameters.</span></span> <span data-ttu-id="7b64b-127">有关详细信息的连接 URI 对于[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="7b64b-127">For more information about the connection URI for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="7b64b-128">如果使用 SAP SNC 库连接到 SAP 系统，设置**UseSnc**连接属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="7b64b-128">If you are using the SAP SNC library to connect to an SAP system, set the **UseSnc** connection property to **True**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="7b64b-129">如果连接参数包含任何保留的字符，则必须指定其作为-处于**URI 属性**选项卡上，即，而无需使用任何转义符。</span><span class="sxs-lookup"><span data-stu-id="7b64b-129">If the connection parameters contain any reserved characters, you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="7b64b-130">但是，如果指定的 URI 中直接**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用正确的转义字符。</span><span class="sxs-lookup"><span data-stu-id="7b64b-130">However, if you specify the URI directly in the **Configure a URI** field and the connection parameters contain reserved characters, you must specify the connection parameters using proper escape characters.</span></span>  

5. <span data-ttu-id="7b64b-131">单击**绑定属性**选项卡，然后指定绑定属性的值，如果你想要针对的操作，任何需要。</span><span class="sxs-lookup"><span data-stu-id="7b64b-131">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="7b64b-132">例如，如果你想要针对 ReceiveIdoc 操作则必须设置**ReceiveIdocFormat**属性绑定到字符串。</span><span class="sxs-lookup"><span data-stu-id="7b64b-132">For example, if you want to target a ReceiveIdoc operation you must set the **ReceiveIdocFormat** binding property to String.</span></span> <span data-ttu-id="7b64b-133">有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="7b64b-133">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="7b64b-134">如果您正在生成元数据中使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]并且选择了现有 WCF SAP 发送端口，不需要指定绑定属性。</span><span class="sxs-lookup"><span data-stu-id="7b64b-134">If you are generating metadata using [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] and you selected an existing WCF-SAP send port, you need not specify the binding properties.</span></span> <span data-ttu-id="7b64b-135">绑定属性是从发送端口配置中选取。</span><span class="sxs-lookup"><span data-stu-id="7b64b-135">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="7b64b-136">但是，您可以选择指定如果任何，则需要在设计时的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="7b64b-136">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="7b64b-137">在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。</span><span class="sxs-lookup"><span data-stu-id="7b64b-137">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="7b64b-138">但是，在运行时指定的发送端口配置中的绑定属性的值将适用。</span><span class="sxs-lookup"><span data-stu-id="7b64b-138">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  
   > 
   > [!IMPORTANT]
   >  <span data-ttu-id="7b64b-139">如果使用 SAP SNC 库连接到 SAP 系统，设置**SncLibrary**并**必须提供 SncPartnerName**为适当的值。</span><span class="sxs-lookup"><span data-stu-id="7b64b-139">If you are using the SAP SNC library to connect to an SAP system, set the **SncLibrary** and **SncPartnerName** to appropriate values.</span></span>  
   > 
   >  <span data-ttu-id="7b64b-140">**SncLibrary**绑定属性采用的路径和使用 SNC 连接到 SAP 系统所需的 Dll 的文件名。</span><span class="sxs-lookup"><span data-stu-id="7b64b-140">The **SncLibrary** binding property takes the path and the filename of the DLLs required for using SNC to connect to an SAP system.</span></span> <span data-ttu-id="7b64b-141">这些 Dll 必须在与 SAP 客户端计算机上存在和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="7b64b-141">These DLLs must be present on the computer with the SAP client and [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] installed.</span></span> <span data-ttu-id="7b64b-142">有关详细信息请参阅[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装指南位于\<安装指南\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents。</span><span class="sxs-lookup"><span data-stu-id="7b64b-142">For more information see the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation guide available at \<installation guide\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.</span></span>  
   > 
   >  <span data-ttu-id="7b64b-143">**SncPartnerName**绑定属性采用的通信合作伙伴 SNC 名称。</span><span class="sxs-lookup"><span data-stu-id="7b64b-143">The **SncPartnerName** binding property takes the SNC name of the communication partner.</span></span>  

6. <span data-ttu-id="7b64b-144">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="7b64b-144">Click **OK**.</span></span>  

7. <span data-ttu-id="7b64b-145">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="7b64b-145">Click **Connect**.</span></span> <span data-ttu-id="7b64b-146">建立连接后，连接状态显示为**已连接**。</span><span class="sxs-lookup"><span data-stu-id="7b64b-146">After the connection is established, the connection status is shown as **Connected**.</span></span>  

    <span data-ttu-id="7b64b-147">下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。</span><span class="sxs-lookup"><span data-stu-id="7b64b-147">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span> <span data-ttu-id="7b64b-148">图形用户界面是适用于[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7b64b-148">The graphical user interface is same for the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

    <span data-ttu-id="7b64b-149">![使用适配器服务连接对话框](../../adapters-and-accelerators/adapter-sap/media/00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0.gif "00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0")</span><span class="sxs-lookup"><span data-stu-id="7b64b-149">![Consume Adapter Service dialog box connected](../../adapters-and-accelerators/adapter-sap/media/00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0.gif "00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0")</span></span>  

    <span data-ttu-id="7b64b-150">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]显示包含可以调用在 SAP 系统中的各种项目的不同节点。</span><span class="sxs-lookup"><span data-stu-id="7b64b-150">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] displays different nodes containing various artifacts that can be invoked in an SAP system.</span></span> <span data-ttu-id="7b64b-151">例如， **RFC**节点包含所有连接到 SAP 系统中提供的 Rfc。</span><span class="sxs-lookup"><span data-stu-id="7b64b-151">For example, the **RFC** node contains all the RFCs available in the SAP system you connected to.</span></span> <span data-ttu-id="7b64b-152">有关这些节点的详细信息，请参阅[元数据节点 Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)。</span><span class="sxs-lookup"><span data-stu-id="7b64b-152">For more information about these nodes, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="7b64b-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="7b64b-153">See Also</span></span>  
 [<span data-ttu-id="7b64b-154">在 Visual Studio 中连接到 SAP 系统</span><span class="sxs-lookup"><span data-stu-id="7b64b-154">Connect to the SAP System in Visual Studio</span></span>](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)