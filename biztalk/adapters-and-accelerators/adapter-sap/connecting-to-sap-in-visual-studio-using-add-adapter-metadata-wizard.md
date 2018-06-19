---
title: Visual Studio 中使用连接到 SAP 添加适配器元数据向导 |Microsoft 文档
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
ms.openlocfilehash: db24d079dc428c69733e36141280504f97728b26
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966235"
---
# <a name="connecting-to-sap-in-visual-studio-using-add-adapter-metadata-wizard"></a><span data-ttu-id="8610f-102">Visual Studio 中使用连接到 SAP 添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="8610f-102">Connecting to SAP in Visual Studio Using Add Adapter Metadata Wizard</span></span>
<span data-ttu-id="8610f-103">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]名称还公开为 BizTalk 适配器，因此，你可以使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]若要为你想要在使用该适配器的 SAP 系统上执行的操作生成架构。</span><span class="sxs-lookup"><span data-stu-id="8610f-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is also exposed as a BizTalk adapter and hence, you can use the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] to generate schema for the operations you want to perform on an SAP system using the adapter.</span></span>  
  
## <a name="connecting-to-an-sap-system-using-add-adapter-metadata-wizard"></a><span data-ttu-id="8610f-104">连接到 SAP 系统使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="8610f-104">Connecting to an SAP System Using Add Adapter Metadata Wizard</span></span>  
 <span data-ttu-id="8610f-105">执行以下步骤以连接到 SAP 系统使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8610f-105">Perform the following steps to connect to an SAP system using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
#### <a name="to-connect-to-an-sap-system"></a><span data-ttu-id="8610f-106">若要连接到 SAP 系统</span><span class="sxs-lookup"><span data-stu-id="8610f-106">To connect to an SAP system</span></span>  
  
1.  <span data-ttu-id="8610f-107">若要使用连接[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]BizTalk 解决方案中：</span><span class="sxs-lookup"><span data-stu-id="8610f-107">To connect using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] in a BizTalk solution:</span></span>  
  
    1.  <span data-ttu-id="8610f-108">创建 BizTalk 项目使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8610f-108">Create a BizTalk project using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
    2.  <span data-ttu-id="8610f-109">右键单击解决方案资源管理器中的项目名称，指向**添加**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="8610f-109">Right-click the project name in Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
    3.  <span data-ttu-id="8610f-110">在**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8610f-110">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
        |<span data-ttu-id="8610f-111">使用此选项</span><span class="sxs-lookup"><span data-stu-id="8610f-111">Use this</span></span>|<span data-ttu-id="8610f-112">执行的操作</span><span class="sxs-lookup"><span data-stu-id="8610f-112">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="8610f-113">**类别**</span><span class="sxs-lookup"><span data-stu-id="8610f-113">**Categories**</span></span>|<span data-ttu-id="8610f-114">单击**添加适配器**。</span><span class="sxs-lookup"><span data-stu-id="8610f-114">Click **Add Adapter**.</span></span>|  
        |<span data-ttu-id="8610f-115">**模板**</span><span class="sxs-lookup"><span data-stu-id="8610f-115">**Templates**</span></span>|<span data-ttu-id="8610f-116">单击**添加适配器元数据**。</span><span class="sxs-lookup"><span data-stu-id="8610f-116">Click **Add Adapter Metadata**.</span></span>|  
  
    4.  <span data-ttu-id="8610f-117">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="8610f-117">Click **Add**.</span></span> <span data-ttu-id="8610f-118">此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。</span><span class="sxs-lookup"><span data-stu-id="8610f-118">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  
  
    5.  <span data-ttu-id="8610f-119">在添加适配器向导中，选择**WCF SAP**。</span><span class="sxs-lookup"><span data-stu-id="8610f-119">In the Add Adapter Wizard, select **WCF-SAP**.</span></span> <span data-ttu-id="8610f-120">选择的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装和 BizTalk 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="8610f-120">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="8610f-121">如果你已经在 BizTalk 中配置 WCF SAP 端口，选择从端口**端口**列表。</span><span class="sxs-lookup"><span data-stu-id="8610f-121">If you already have a WCF-SAP port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
    6.  <span data-ttu-id="8610f-122">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="8610f-122">Click **Next**.</span></span>  
  
2.  <span data-ttu-id="8610f-123">从**选择的绑定**下拉列表中，选择**sapBinding**单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="8610f-123">From the **Select a binding** drop-down list, select **sapBinding** and click **Configure**.</span></span>  
  
3.  <span data-ttu-id="8610f-124">在**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表框中，选择**用户名**和指定的用户名和密码以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="8610f-124">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the SAP system.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="8610f-125">如果你使用 SAP 安全网络连接 (SNC) 库连接到 SAP 系统，则不指定用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="8610f-125">If you are using the SAP Secure Network Connection (SNC) library to connect to an SAP system, do not specify a username and password.</span></span>  
  
4.  <span data-ttu-id="8610f-126">单击**URI 属性**选项卡上，并指定连接参数的值。</span><span class="sxs-lookup"><span data-stu-id="8610f-126">Click the **URI Properties** tab and specify values for the connection parameters.</span></span> <span data-ttu-id="8610f-127">有关连接 URI 的详细信息为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="8610f-127">For more information about the connection URI for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="8610f-128">如果你使用 SAP SNC 库连接到 SAP 系统，设置**UseSnc**连接属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="8610f-128">If you are using the SAP SNC library to connect to an SAP system, set the **UseSnc** connection property to **True**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8610f-129">如果连接参数包含任何保留的字符，则必须指定它们作为-处于**URI 属性**选项卡上，即，而无需使用任何转义字符。</span><span class="sxs-lookup"><span data-stu-id="8610f-129">If the connection parameters contain any reserved characters, you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="8610f-130">但是，如果你指定直接在 URI**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用适当的转义字符。</span><span class="sxs-lookup"><span data-stu-id="8610f-130">However, if you specify the URI directly in the **Configure a URI** field and the connection parameters contain reserved characters, you must specify the connection parameters using proper escape characters.</span></span>  
  
5.  <span data-ttu-id="8610f-131">单击**绑定属性**选项卡上，然后指定绑定属性的值，如果任何，所需的要设定为目标的操作。</span><span class="sxs-lookup"><span data-stu-id="8610f-131">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="8610f-132">例如，如果你想要针对 ReceiveIdoc 操作则必须设置**ReceiveIdocFormat**将属性绑定到字符串。</span><span class="sxs-lookup"><span data-stu-id="8610f-132">For example, if you want to target a ReceiveIdoc operation you must set the **ReceiveIdocFormat** binding property to String.</span></span> <span data-ttu-id="8610f-133">有关绑定属性的详细信息，请参阅[了解针对 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="8610f-133">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8610f-134">如果正在生成元数据中使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]并且选择现有 WCF SAP 发送端口，你不需要指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="8610f-134">If you are generating metadata using [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] and you selected an existing WCF-SAP send port, you need not specify the binding properties.</span></span> <span data-ttu-id="8610f-135">绑定属性是从发送端口配置中选取。</span><span class="sxs-lookup"><span data-stu-id="8610f-135">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="8610f-136">但是，你可以选择指定所需在设计时，如果任何绑定属性。</span><span class="sxs-lookup"><span data-stu-id="8610f-136">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="8610f-137">在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。</span><span class="sxs-lookup"><span data-stu-id="8610f-137">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="8610f-138">但是，在运行时指定中发送端口配置的绑定属性的值将适用。</span><span class="sxs-lookup"><span data-stu-id="8610f-138">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="8610f-139">如果你使用 SAP SNC 库连接到 SAP 系统，设置**SncLibrary**和**SncPartnerName**为适当的值。</span><span class="sxs-lookup"><span data-stu-id="8610f-139">If you are using the SAP SNC library to connect to an SAP system, set the **SncLibrary** and **SncPartnerName** to appropriate values.</span></span>  
    >   
    >  <span data-ttu-id="8610f-140">**SncLibrary**绑定属性采用的路径以及使用 SNC 连接到 SAP 系统所需的 Dll 的文件名。</span><span class="sxs-lookup"><span data-stu-id="8610f-140">The **SncLibrary** binding property takes the path and the filename of the DLLs required for using SNC to connect to an SAP system.</span></span> <span data-ttu-id="8610f-141">这些 Dll 必须存在 SAP 客户端计算机上和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="8610f-141">These DLLs must be present on the computer with the SAP client and [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] installed.</span></span> <span data-ttu-id="8610f-142">有关详细信息请参阅[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装指南位于\<安装指南\>: files\microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents。</span><span class="sxs-lookup"><span data-stu-id="8610f-142">For more information see the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation guide available at \<installation guide\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.</span></span>  
    >   
    >  <span data-ttu-id="8610f-143">**SncPartnerName**绑定属性将通信合作伙伴的 SNC 名称。</span><span class="sxs-lookup"><span data-stu-id="8610f-143">The **SncPartnerName** binding property takes the SNC name of the communication partner.</span></span>  
  
6.  <span data-ttu-id="8610f-144">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="8610f-144">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="8610f-145">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="8610f-145">Click **Connect**.</span></span> <span data-ttu-id="8610f-146">建立连接后，连接状态将显示为**已连接**。</span><span class="sxs-lookup"><span data-stu-id="8610f-146">After the connection is established, the connection status is shown as **Connected**.</span></span>  
  
     <span data-ttu-id="8610f-147">下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。</span><span class="sxs-lookup"><span data-stu-id="8610f-147">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span> <span data-ttu-id="8610f-148">图形用户界面是适用于[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8610f-148">The graphical user interface is same for the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
     <span data-ttu-id="8610f-149">![使用适配器服务连接的对话框](../../adapters-and-accelerators/adapter-sap/media/00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0.gif "00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0")</span><span class="sxs-lookup"><span data-stu-id="8610f-149">![Consume Adapter Service dialog box connected](../../adapters-and-accelerators/adapter-sap/media/00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0.gif "00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0")</span></span>  
  
     <span data-ttu-id="8610f-150">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]显示包含可以在某个 SAP 系统中调用的各种项目的不同节点。</span><span class="sxs-lookup"><span data-stu-id="8610f-150">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] displays different nodes containing various artifacts that can be invoked in an SAP system.</span></span> <span data-ttu-id="8610f-151">例如， **RFC**节点包含在连接到 SAP 系统中可用的所有 Rfc。</span><span class="sxs-lookup"><span data-stu-id="8610f-151">For example, the **RFC** node contains all the RFCs available in the SAP system you connected to.</span></span> <span data-ttu-id="8610f-152">有关这些节点的详细信息，请参阅[元数据的节点 Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)。</span><span class="sxs-lookup"><span data-stu-id="8610f-152">For more information about these nodes, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8610f-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8610f-153">See Also</span></span>  
 [<span data-ttu-id="8610f-154">在 Visual Studio 中连接到 SAP 系统</span><span class="sxs-lookup"><span data-stu-id="8610f-154">Connect to the SAP System in Visual Studio</span></span>](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)