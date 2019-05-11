---
title: Visual Studio 中使用连接到 SAP 使用适配器服务外接程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4f7d57a-fd88-4420-b893-49f42b449597
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36897cf2102858fb43f79c88ea24dc7954df3b75
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373592"
---
# <a name="connecting-to-sap-in-visual-studio-using-consume-adapter-service-add-in"></a><span data-ttu-id="75b66-102">Visual Studio 中使用连接到 SAP 使用适配器服务外接程序</span><span class="sxs-lookup"><span data-stu-id="75b66-102">Connecting to SAP in Visual Studio Using Consume Adapter Service Add-in</span></span>
<span data-ttu-id="75b66-103">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]安装 WCF LOB 适配器 SDK 时会安装。</span><span class="sxs-lookup"><span data-stu-id="75b66-103">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] is installed when you install WCF LOB Adapter SDK.</span></span> <span data-ttu-id="75b66-104">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]加载在计算机上安装的所有 WCF 自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="75b66-104">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] loads all the WCF-Custom bindings installed on the computer.</span></span> <span data-ttu-id="75b66-105">若要连接到 SAP 系统使用基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在 BizTalk 项目中，必须使用**sapbinding**。</span><span class="sxs-lookup"><span data-stu-id="75b66-105">To connect to SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in a BizTalk project, you must use the **sapbinding**.</span></span>  

 <span data-ttu-id="75b66-106">本主题说明了如何使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="75b66-106">This topic provides instructions on how to use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  

## <a name="connecting-to-an-sap-system-using-consume-adapter-service-add-in"></a><span data-ttu-id="75b66-107">连接到 SAP 系统使用使用适配器服务外接程序</span><span class="sxs-lookup"><span data-stu-id="75b66-107">Connecting to an SAP System Using Consume Adapter Service Add-in</span></span>  
 <span data-ttu-id="75b66-108">执行以下步骤连接到 SAP 系统使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="75b66-108">Perform the following steps to connect to an SAP system using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  

#### <a name="to-connect-to-an-sap-system"></a><span data-ttu-id="75b66-109">若要连接到 SAP 系统</span><span class="sxs-lookup"><span data-stu-id="75b66-109">To connect to an SAP system</span></span>  

1. <span data-ttu-id="75b66-110">若要使用连接[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]BizTalk 解决方案中：</span><span class="sxs-lookup"><span data-stu-id="75b66-110">To connect using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] in a BizTalk solution:</span></span>  

   1. <span data-ttu-id="75b66-111">创建 BizTalk 项目使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="75b66-111">Create a BizTalk project using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  

   2. <span data-ttu-id="75b66-112">右键单击解决方案资源管理器中的项目名称，指向**外**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="75b66-112">Right-click the project name in Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  

   3. <span data-ttu-id="75b66-113">在中**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="75b66-113">In the **Add Generated Items** dialog box, do the following:</span></span>  


      |    <span data-ttu-id="75b66-114">使用此选项</span><span class="sxs-lookup"><span data-stu-id="75b66-114">Use this</span></span>    |             <span data-ttu-id="75b66-115">执行的操作</span><span class="sxs-lookup"><span data-stu-id="75b66-115">To do this</span></span>             |
      |----------------|------------------------------------|
      | <span data-ttu-id="75b66-116">**类别**</span><span class="sxs-lookup"><span data-stu-id="75b66-116">**Categories**</span></span> | <span data-ttu-id="75b66-117">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="75b66-117">Click **Consume Adapter Service**.</span></span> |
      | <span data-ttu-id="75b66-118">**模板**</span><span class="sxs-lookup"><span data-stu-id="75b66-118">**Templates**</span></span>  | <span data-ttu-id="75b66-119">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="75b66-119">Click **Consume Adapter Service**.</span></span> |


   4. <span data-ttu-id="75b66-120">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="75b66-120">Click **Add**.</span></span> <span data-ttu-id="75b66-121">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]随即打开。</span><span class="sxs-lookup"><span data-stu-id="75b66-121">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] opens.</span></span>  

2. <span data-ttu-id="75b66-122">从**选择绑定**下拉列表中，选择**sapBinding**然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="75b66-122">From the **Select a binding** drop-down list, select **sapBinding** and click **Configure**.</span></span>  

3. <span data-ttu-id="75b66-123">在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表框中，选择**用户名**并指定用户名和密码以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="75b66-123">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the SAP system.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="75b66-124">如果使用 SAP 安全网络连接 (SNC) 库来连接到 SAP 系统，则不指定用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="75b66-124">If you are using the SAP Secure Network Connection (SNC) library to connect to an SAP system, do not specify a username and password.</span></span>  

4. <span data-ttu-id="75b66-125">单击**URI 属性**选项卡，指定连接参数的值。</span><span class="sxs-lookup"><span data-stu-id="75b66-125">Click the **URI Properties** tab and specify values for the connection parameters.</span></span> <span data-ttu-id="75b66-126">有关详细信息的连接 URI 对于[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="75b66-126">For more information about the connection URI for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="75b66-127">如果使用 SAP SNC 库连接到 SAP 系统，设置**UseSnc**连接属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="75b66-127">If you are using the SAP SNC library to connect to an SAP system, set the **UseSnc** connection property to **True**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="75b66-128">如果连接参数包含任何保留的字符，则必须指定其作为-处于**URI 属性**选项卡上，即，而无需使用任何转义符。</span><span class="sxs-lookup"><span data-stu-id="75b66-128">If the connection parameters contain any reserved characters, you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="75b66-129">但是，如果指定的 URI 中直接**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用正确的转义字符。</span><span class="sxs-lookup"><span data-stu-id="75b66-129">However, if you specify the URI directly in the **Configure a URI** field and the connection parameters contain reserved characters, you must specify the connection parameters using proper escape characters.</span></span>  

5. <span data-ttu-id="75b66-130">单击**绑定属性**选项卡，然后指定绑定属性的值，如果你想要针对的操作，任何需要。</span><span class="sxs-lookup"><span data-stu-id="75b66-130">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="75b66-131">例如，如果你想要针对 ReceiveIdoc 操作则必须设置**ReceiveIdocFormat**属性绑定到字符串。</span><span class="sxs-lookup"><span data-stu-id="75b66-131">For example, if you want to target a ReceiveIdoc operation you must set the **ReceiveIdocFormat** binding property to String.</span></span> <span data-ttu-id="75b66-132">有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="75b66-132">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="75b66-133">如果使用 SAP SNC 库连接到 SAP 系统，设置**SncLibrary**并**必须提供 SncPartnerName**为适当的值。</span><span class="sxs-lookup"><span data-stu-id="75b66-133">If you are using the SAP SNC library to connect to an SAP system, set the **SncLibrary** and **SncPartnerName** to appropriate values.</span></span>  
   > 
   >  <span data-ttu-id="75b66-134">**SncLibrary**绑定属性采用的路径和使用 SNC 连接到 SAP 系统所需的 Dll 的文件名。</span><span class="sxs-lookup"><span data-stu-id="75b66-134">The **SncLibrary** binding property takes the path and the filename of the DLLs required for using SNC to connect to an SAP system.</span></span> <span data-ttu-id="75b66-135">这些 Dll 必须在与 SAP 客户端计算机上存在和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="75b66-135">These DLLs must be present on the computer with the SAP client and [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] installed.</span></span> <span data-ttu-id="75b66-136">有关详细信息请参阅[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装指南位于\<安装指南\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents。</span><span class="sxs-lookup"><span data-stu-id="75b66-136">For more information see the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation guide available at \<installation guide\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.</span></span>  
   > 
   >  <span data-ttu-id="75b66-137">**SncPartnerName**绑定属性采用的通信合作伙伴 SNC 名称。</span><span class="sxs-lookup"><span data-stu-id="75b66-137">The **SncPartnerName** binding property takes the SNC name of the communication partner.</span></span>  

6. <span data-ttu-id="75b66-138">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="75b66-138">Click **OK**.</span></span>  

7. <span data-ttu-id="75b66-139">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="75b66-139">Click **Connect**.</span></span> <span data-ttu-id="75b66-140">建立连接后，连接状态显示为**已连接**。</span><span class="sxs-lookup"><span data-stu-id="75b66-140">After the connection is established, the connection status is shown as **Connected**.</span></span>  

    <span data-ttu-id="75b66-141">下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。</span><span class="sxs-lookup"><span data-stu-id="75b66-141">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span>  

    <span data-ttu-id="75b66-142">![使用适配器服务连接对话框](../../adapters-and-accelerators/adapter-sap/media/00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0.gif "00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0")</span><span class="sxs-lookup"><span data-stu-id="75b66-142">![Consume Adapter Service dialog box connected](../../adapters-and-accelerators/adapter-sap/media/00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0.gif "00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0")</span></span>  

    <span data-ttu-id="75b66-143">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]显示包含可以调用在 SAP 系统中的各种项目的不同节点。</span><span class="sxs-lookup"><span data-stu-id="75b66-143">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] displays different nodes containing various artifacts that can be invoked in an SAP system.</span></span> <span data-ttu-id="75b66-144">例如， **RFC**节点包含所有连接到 SAP 系统中提供的 Rfc。</span><span class="sxs-lookup"><span data-stu-id="75b66-144">For example, the **RFC** node contains all the RFCs available in the SAP system you connected to.</span></span> <span data-ttu-id="75b66-145">有关这些节点的详细信息，请参阅[元数据节点 Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)。</span><span class="sxs-lookup"><span data-stu-id="75b66-145">For more information about these nodes, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="75b66-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="75b66-146">See Also</span></span>  
 [<span data-ttu-id="75b66-147">在 Visual Studio 中连接到 SAP 系统</span><span class="sxs-lookup"><span data-stu-id="75b66-147">Connect to the SAP System in Visual Studio</span></span>](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)