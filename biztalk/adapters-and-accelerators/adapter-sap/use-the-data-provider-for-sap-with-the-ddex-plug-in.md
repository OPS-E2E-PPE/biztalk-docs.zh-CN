---
title: 使用包含 DDEX 插件的 SAP 数据提供程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DDEX plug-in
- DDEX plug-in, Data Provider for SAP
- Data Provider for SAP, using with DDEX plug-in
ms.assetid: b16c8634-172a-4630-87ed-2073a75afdec
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 344467367e5745ab089c3f70be017759d22ba8b1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970686"
---
# <a name="use-the-data-provider-for-sap-with-the-ddex-plug-in"></a><span data-ttu-id="da7a1-102">使用包含 DDEX 插件的 SAP 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="da7a1-102">Use the Data Provider for SAP with the DDEX Plug-in</span></span>
<span data-ttu-id="da7a1-103">如果您选择安装[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]连同[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装，安装程序将安装[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]DDEX 插件。</span><span class="sxs-lookup"><span data-stu-id="da7a1-103">If you chose to install the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] along with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation, the setup program installs a [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX plug-in.</span></span> <span data-ttu-id="da7a1-104">您可以使用此插件来浏览 SAP 对象使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="da7a1-104">You can use this plug-in to browse SAP objects using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="da7a1-105">本部分提供有关使用 DDEX 插件的信息。</span><span class="sxs-lookup"><span data-stu-id="da7a1-105">This section provides information about using the DDEX plug-in.</span></span>  
  
 <span data-ttu-id="da7a1-106">您可以使用该插件以建立与 SAP 系统从 SAP 系统中，添加表并从 SAP 系统中添加函数模块。</span><span class="sxs-lookup"><span data-stu-id="da7a1-106">You can use the plug-in to establish connectivity with the SAP system, add tables from the SAP system, and add function modules from the SAP system.</span></span> <span data-ttu-id="da7a1-107">添加表和函数模块使用 Visual Studio 插件后，新添加的表和函数模块会反映在 SAPDiscoveredObjects.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="da7a1-107">After you have added the tables and function modules using the Visual Studio plug-in, the newly added tables and function modules are reflected in the SAPDiscoveredObjects.xml file.</span></span> <span data-ttu-id="da7a1-108">有关此文件的详细信息，请参阅[有关 SAPDiscoveredObjects.xml 文件在 SAP 中](../../adapters-and-accelerators/adapter-sap/about-the-sapdiscoveredobjects-xml-file-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="da7a1-108">For more information about this file, see [About the SAPDiscoveredObjects.xml File in SAP](../../adapters-and-accelerators/adapter-sap/about-the-sapdiscoveredobjects-xml-file-in-sap.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="da7a1-109">必要條件</span><span class="sxs-lookup"><span data-stu-id="da7a1-109">Prerequisites</span></span>  
 <span data-ttu-id="da7a1-110">请确保您选择安装[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]连同[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="da7a1-110">Make sure you chose to install the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] along with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation.</span></span>  
  
### <a name="to-connect-to-an-sap-system-using-the-ddex-plug-in"></a><span data-ttu-id="da7a1-111">若要连接到 SAP 系统使用的 DDEX 插件</span><span class="sxs-lookup"><span data-stu-id="da7a1-111">To connect to an SAP system using the DDEX plug-in</span></span>  
  
1. <span data-ttu-id="da7a1-112">启动 Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="da7a1-112">Start Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="da7a1-113">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，然后在**视图**菜单中，单击**服务器资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="da7a1-113">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **View** menu, click **Server Explorer**.</span></span>  
  
3. <span data-ttu-id="da7a1-114">在中**服务器资源管理器**，右键单击**数据连接**，然后选择**添加连接**。</span><span class="sxs-lookup"><span data-stu-id="da7a1-114">In the **Server Explorer**, right-click **Data Connections**, and select **Add Connection**.</span></span>  
  
4. <span data-ttu-id="da7a1-115">在中**更改数据源**对话框中，从**数据源**框中，选择**\<其他\>**。</span><span class="sxs-lookup"><span data-stu-id="da7a1-115">In the **Change Data Source** dialog box, from the **Data source** box, select **\<other\>**.</span></span>  
  
5. <span data-ttu-id="da7a1-116">从**数据提供程序**下拉列表中，选择 **.NET Framework Data Provider for mySAP Business Suite**然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="da7a1-116">From the **Data provider** drop-down list, select **.NET Framework Data Provider for mySAP Business Suite** and click **OK**.</span></span> <span data-ttu-id="da7a1-117">**添加连接**对话框随即打开。</span><span class="sxs-lookup"><span data-stu-id="da7a1-117">The **Add Connection** dialog box opens.</span></span>  
  
6. <span data-ttu-id="da7a1-118">**添加连接**对话框将列出要连接到 SAP 系统的其他连接参数。</span><span class="sxs-lookup"><span data-stu-id="da7a1-118">The **Add Connection** dialog box lists the different connection parameters to connect to an SAP system.</span></span> <span data-ttu-id="da7a1-119">典型的连接字符串连接到 SAP 系统使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]要求：</span><span class="sxs-lookup"><span data-stu-id="da7a1-119">A typical connection string to connect to an SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requires:</span></span>  
  
   - <span data-ttu-id="da7a1-120">连接类型的连接参数。</span><span class="sxs-lookup"><span data-stu-id="da7a1-120">The connection parameters for a connection type.</span></span> <span data-ttu-id="da7a1-121">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]支持连接类型 A、 B 和 d。若要连接到 SAP 系统必须提供连接参数的任何*一个*的这些连接类型。</span><span class="sxs-lookup"><span data-stu-id="da7a1-121">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] supports connection types A, B, and D. To connect to an SAP system you must provide connection parameters for any *one* of these connection types.</span></span> <span data-ttu-id="da7a1-122">例如，对于连接类型的必须提供应用程序服务器主机和系统编号的名称。</span><span class="sxs-lookup"><span data-stu-id="da7a1-122">For example, for connection type A, you must provide the name of the application server host and the system number.</span></span>  
  
   - <span data-ttu-id="da7a1-123">要连接到 SAP 系统，如用户名和密码的登录信息。</span><span class="sxs-lookup"><span data-stu-id="da7a1-123">The login information to connect to an SAP system such as username and password.</span></span>  
  
     <span data-ttu-id="da7a1-124">详细了解要连接到 SAP 系统使用的连接字符串[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[了解数据提供程序类型适用于 SAP 连接字符串](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)。</span><span class="sxs-lookup"><span data-stu-id="da7a1-124">For more information about the connection string to connect to an SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Read about Data Provider types for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
     <span data-ttu-id="da7a1-125">在中**添加连接**对话框框中，指定：</span><span class="sxs-lookup"><span data-stu-id="da7a1-125">In the **Add Connection** dialog box, specify:</span></span>  
  
   - <span data-ttu-id="da7a1-126">类型的任何一个连接的连接参数。</span><span class="sxs-lookup"><span data-stu-id="da7a1-126">The connection parameters for any one connection type.</span></span>  
  
   - <span data-ttu-id="da7a1-127">要连接到 SAP 系统的登录信息。</span><span class="sxs-lookup"><span data-stu-id="da7a1-127">The login information to connect to an SAP system.</span></span>  
  
   - <span data-ttu-id="da7a1-128">是否想要启用 SAP GUI 调试。</span><span class="sxs-lookup"><span data-stu-id="da7a1-128">Whether you want to enable SAP GUI debugging.</span></span>  
  
   - <span data-ttu-id="da7a1-129">是否想要使用 RFC SDK 跟踪。</span><span class="sxs-lookup"><span data-stu-id="da7a1-129">Whether you want to use RFC SDK tracing.</span></span>  
  
     <span data-ttu-id="da7a1-130">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="da7a1-130">Click **OK**.</span></span> <span data-ttu-id="da7a1-131">在下，创建一个新的连接节点**数据连接**与上一步中指定的服务器名称的节点。</span><span class="sxs-lookup"><span data-stu-id="da7a1-131">A new connection node is created under the **Data Connections** node with the server name you specified in the previous step.</span></span>  
  
7. <span data-ttu-id="da7a1-132">展开新的连接节点，以查看**表**并**函数模块**节点。</span><span class="sxs-lookup"><span data-stu-id="da7a1-132">Expand the new connection node to view the **Tables** and **Function Modules** nodes.</span></span>  
  
    <span data-ttu-id="da7a1-133">建立连接后，下图显示了服务器资源管理器。</span><span class="sxs-lookup"><span data-stu-id="da7a1-133">The following figure shows the Server Explorer after the connection is established.</span></span>  
  
    <span data-ttu-id="da7a1-134">![DDEX 插件&#45;中用于 SAP ADO.NET 提供程序](../../adapters-and-accelerators/adapter-sap/media/158afc11-9c90-4333-bc62-5901f8d0c794.gif "158afc11-9c90-4333-bc62-5901f8d0c794")</span><span class="sxs-lookup"><span data-stu-id="da7a1-134">![DDEX plug&#45;in for SAP ADO.NET Provider](../../adapters-and-accelerators/adapter-sap/media/158afc11-9c90-4333-bc62-5901f8d0c794.gif "158afc11-9c90-4333-bc62-5901f8d0c794")</span></span>  
  
### <a name="to-add-tables-from-an-sap-system-using-the-ddex-plug-in"></a><span data-ttu-id="da7a1-135">若要从 SAP 系统使用的 DDEX 插件中添加表</span><span class="sxs-lookup"><span data-stu-id="da7a1-135">To add tables from an SAP system using the DDEX plug-in</span></span>  
  
1. <span data-ttu-id="da7a1-136">在中**服务器资源管理器**，右键单击**表**节点，然后单击**搜索和添加表**。</span><span class="sxs-lookup"><span data-stu-id="da7a1-136">In the **Server Explorer**, right-click the **Tables** node and click **Search and Add Tables**.</span></span>  
  
2. <span data-ttu-id="da7a1-137">在中**搜索表名称**文字框中，指定搜索字符串，可以搜索 SAP 系统中的表，然后单击**搜索**。</span><span class="sxs-lookup"><span data-stu-id="da7a1-137">In the **Search table name** text box, specify a search string to search tables in the SAP system, and click **Search**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="da7a1-138">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]支持星号 （\*） 通配符字符的使用，以搜索表。</span><span class="sxs-lookup"><span data-stu-id="da7a1-138">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] supports the use of only the asterisk (\*) wildcard character for searching tables.</span></span>  
  
3. <span data-ttu-id="da7a1-139">**搜索结果**框列出了满足搜索条件的表名。</span><span class="sxs-lookup"><span data-stu-id="da7a1-139">The **Search results** box lists the table names that satisfy the search criteria.</span></span>  
  
    <span data-ttu-id="da7a1-140">![DDEX 插件&#45;中搜索和添加表名称对话框](../../adapters-and-accelerators/adapter-sap/media/737fc9c3-5258-4693-a2f3-5b5b8d2483e9.gif "737fc9c3-5258-4693-a2f3-5b5b8d2483e9")</span><span class="sxs-lookup"><span data-stu-id="da7a1-140">![DDEX plug&#45;in Search and Add Tables name dialog box](../../adapters-and-accelerators/adapter-sap/media/737fc9c3-5258-4693-a2f3-5b5b8d2483e9.gif "737fc9c3-5258-4693-a2f3-5b5b8d2483e9")</span></span>  
  
4. <span data-ttu-id="da7a1-141">选中你想要添加，然后单击的表相对应的复选框**添加**。</span><span class="sxs-lookup"><span data-stu-id="da7a1-141">Select the check box corresponding to the tables you want to add and click **Add**.</span></span> <span data-ttu-id="da7a1-142">若要选择所有表，请单击**全**。</span><span class="sxs-lookup"><span data-stu-id="da7a1-142">To select all the tables, click **Select All**.</span></span> <span data-ttu-id="da7a1-143">若要清除所有选择，请单击**都清除所有**。</span><span class="sxs-lookup"><span data-stu-id="da7a1-143">To clear all the selections, click **Clear All**.</span></span>  
  
5. <span data-ttu-id="da7a1-144">一个对话框通知你刷新后，会导致添加的表可见**表**节点。</span><span class="sxs-lookup"><span data-stu-id="da7a1-144">A dialog box informs you that the added tables would be visible after you refresh the **Tables** node.</span></span> <span data-ttu-id="da7a1-145">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="da7a1-145">Click **OK**.</span></span>  
  
6. <span data-ttu-id="da7a1-146">右键单击**表**节点，然后选择**刷新**。</span><span class="sxs-lookup"><span data-stu-id="da7a1-146">Right-click the **Tables** node and select **Refresh**.</span></span> <span data-ttu-id="da7a1-147">所选的表的显示下**表**节点。</span><span class="sxs-lookup"><span data-stu-id="da7a1-147">The selected tables appear under the **Tables** node.</span></span> <span data-ttu-id="da7a1-148">单击表名以查看中的表属性**属性**窗格。</span><span class="sxs-lookup"><span data-stu-id="da7a1-148">Click a table name to see the table properties in the **Properties** pane.</span></span>  
  
7. <span data-ttu-id="da7a1-149">展开表名称以查看表的字段。</span><span class="sxs-lookup"><span data-stu-id="da7a1-149">Expand a table name to see the fields for the table.</span></span> <span data-ttu-id="da7a1-150">单击字段名称，请参阅中的字段属性**属性**窗格。</span><span class="sxs-lookup"><span data-stu-id="da7a1-150">Click a field name to see the field properties in the **Properties** pane.</span></span>  
  
### <a name="to-add-rfcs-from-an-sap-system-using-the-ddex-plug-in"></a><span data-ttu-id="da7a1-151">若要从 SAP 系统使用的 DDEX 插件添加 Rfc</span><span class="sxs-lookup"><span data-stu-id="da7a1-151">To add RFCs from an SAP system using the DDEX plug-in</span></span>  
  
1. <span data-ttu-id="da7a1-152">在中**服务器资源管理器**，右键单击**函数模块**节点，然后单击**搜索和添加函数模块**。</span><span class="sxs-lookup"><span data-stu-id="da7a1-152">In the **Server Explorer**, right-click the **Function Modules** node and click **Search and Add Function Modules**.</span></span>  
  
2. <span data-ttu-id="da7a1-153">在中**搜索函数模块**文字框中，指定搜索字符串，可以在 SAP 系统中，搜索函数模块，然后单击**搜索**。</span><span class="sxs-lookup"><span data-stu-id="da7a1-153">In the **Search function module** text box, specify a search string to search function modules in the SAP system, and click **Search**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="da7a1-154">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]支持使用星号 （\*） 通配符字符的搜索功能模块。</span><span class="sxs-lookup"><span data-stu-id="da7a1-154">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] supports the use of only the asterisk (\*) wildcard character for searching functional modules.</span></span>  
  
3. <span data-ttu-id="da7a1-155">**搜索结果**框列出了满足搜索条件的函数模块。</span><span class="sxs-lookup"><span data-stu-id="da7a1-155">The **Search results** box lists the function modules that satisfy the search criteria.</span></span>  
  
    <span data-ttu-id="da7a1-156">![DDEX 插件&#45;在搜索和添加模块对话框](../../adapters-and-accelerators/adapter-sap/media/8c7f9081-80aa-4bfe-8f06-2c751758ddd0.gif "8c7f9081-80aa-4bfe-8f06-2c751758ddd0")</span><span class="sxs-lookup"><span data-stu-id="da7a1-156">![DDEX plug&#45;in Search and Add Modules dialog box](../../adapters-and-accelerators/adapter-sap/media/8c7f9081-80aa-4bfe-8f06-2c751758ddd0.gif "8c7f9081-80aa-4bfe-8f06-2c751758ddd0")</span></span>  
  
4. <span data-ttu-id="da7a1-157">选择你想要添加，然后单击的函数模块到相应的复选框**添加**。</span><span class="sxs-lookup"><span data-stu-id="da7a1-157">Select the check box corresponding to the function modules you want to add and click **Add**.</span></span> <span data-ttu-id="da7a1-158">若要选择的所有模块，请单击**全**。</span><span class="sxs-lookup"><span data-stu-id="da7a1-158">To select all the modules, click **Select All**.</span></span> <span data-ttu-id="da7a1-159">若要清除所有选择，请单击**都清除所有**。</span><span class="sxs-lookup"><span data-stu-id="da7a1-159">To clear all the selections, click **Clear All**.</span></span>  
  
5. <span data-ttu-id="da7a1-160">一个对话框通知你刷新后，会导致添加的函数模块可见**函数模块**节点。</span><span class="sxs-lookup"><span data-stu-id="da7a1-160">A dialog box informs you that the added function modules would be visible after you refresh the **Function Modules** node.</span></span> <span data-ttu-id="da7a1-161">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="da7a1-161">Click **OK**.</span></span>  
  
6. <span data-ttu-id="da7a1-162">右键单击**函数模块**节点，然后选择**刷新**。</span><span class="sxs-lookup"><span data-stu-id="da7a1-162">Right-click the **Function Modules** node and select **Refresh**.</span></span> <span data-ttu-id="da7a1-163">所选的函数模块显示下**函数模块**节点。</span><span class="sxs-lookup"><span data-stu-id="da7a1-163">The selected function modules appear under the **Function Modules** node.</span></span> <span data-ttu-id="da7a1-164">单击要查看的属性中的函数模块名称**属性**窗格。</span><span class="sxs-lookup"><span data-stu-id="da7a1-164">Click a function module name to see the properties in the **Properties** pane.</span></span>  
  
7. <span data-ttu-id="da7a1-165">展开的函数模块名称，若要查看用于导入、 导出、 更改和表参数节点。</span><span class="sxs-lookup"><span data-stu-id="da7a1-165">Expand a function module name to see nodes for import, export, changing, and table parameters.</span></span>  
  
8. <span data-ttu-id="da7a1-166">展开**导入**节点以列出函数模块的导入参数。</span><span class="sxs-lookup"><span data-stu-id="da7a1-166">Expand the **Import** node to list the import parameters for the function module.</span></span> <span data-ttu-id="da7a1-167">同样，展开**导出**并**表**节点，以便查看函数模块的导出和表参数的列表。</span><span class="sxs-lookup"><span data-stu-id="da7a1-167">Similarly, expand the **Export** and **Tables** nodes to see the list of export and table parameters for the function module.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da7a1-168">请参阅</span><span class="sxs-lookup"><span data-stu-id="da7a1-168">See Also</span></span>  
 [<span data-ttu-id="da7a1-169">使用 mySAP Business Suite 的 .NET Framework 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="da7a1-169">Use the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)