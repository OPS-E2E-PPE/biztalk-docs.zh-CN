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
# <a name="use-the-data-provider-for-sap-with-the-ddex-plug-in"></a>使用包含 DDEX 插件的 SAP 数据提供程序
如果您选择安装[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]连同[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装，安装程序将安装[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]DDEX 插件。 您可以使用此插件来浏览 SAP 对象使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 本部分提供有关使用 DDEX 插件的信息。  
  
 您可以使用该插件以建立与 SAP 系统从 SAP 系统中，添加表并从 SAP 系统中添加函数模块。 添加表和函数模块使用 Visual Studio 插件后，新添加的表和函数模块会反映在 SAPDiscoveredObjects.xml 文件。 有关此文件的详细信息，请参阅[有关 SAPDiscoveredObjects.xml 文件在 SAP 中](../../adapters-and-accelerators/adapter-sap/about-the-sapdiscoveredobjects-xml-file-in-sap.md)。  
  
## <a name="prerequisites"></a>必要條件  
 请确保您选择安装[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]连同[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装。  
  
### <a name="to-connect-to-an-sap-system-using-the-ddex-plug-in"></a>若要连接到 SAP 系统使用的 DDEX 插件  
  
1. 启动 Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
2. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，然后在**视图**菜单中，单击**服务器资源管理器**。  
  
3. 在中**服务器资源管理器**，右键单击**数据连接**，然后选择**添加连接**。  
  
4. 在中**更改数据源**对话框中，从**数据源**框中，选择**\<其他\>**。  
  
5. 从**数据提供程序**下拉列表中，选择 **.NET Framework Data Provider for mySAP Business Suite**然后单击**确定**。 **添加连接**对话框随即打开。  
  
6. **添加连接**对话框将列出要连接到 SAP 系统的其他连接参数。 典型的连接字符串连接到 SAP 系统使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]要求：  
  
   - 连接类型的连接参数。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]支持连接类型 A、 B 和 d。若要连接到 SAP 系统必须提供连接参数的任何*一个*的这些连接类型。 例如，对于连接类型的必须提供应用程序服务器主机和系统编号的名称。  
  
   - 要连接到 SAP 系统，如用户名和密码的登录信息。  
  
     详细了解要连接到 SAP 系统使用的连接字符串[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[了解数据提供程序类型适用于 SAP 连接字符串](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)。  
  
     在中**添加连接**对话框框中，指定：  
  
   - 类型的任何一个连接的连接参数。  
  
   - 要连接到 SAP 系统的登录信息。  
  
   - 是否想要启用 SAP GUI 调试。  
  
   - 是否想要使用 RFC SDK 跟踪。  
  
     单击“确定” 。 在下，创建一个新的连接节点**数据连接**与上一步中指定的服务器名称的节点。  
  
7. 展开新的连接节点，以查看**表**并**函数模块**节点。  
  
    建立连接后，下图显示了服务器资源管理器。  
  
    ![DDEX 插件&#45;中用于 SAP ADO.NET 提供程序](../../adapters-and-accelerators/adapter-sap/media/158afc11-9c90-4333-bc62-5901f8d0c794.gif "158afc11-9c90-4333-bc62-5901f8d0c794")  
  
### <a name="to-add-tables-from-an-sap-system-using-the-ddex-plug-in"></a>若要从 SAP 系统使用的 DDEX 插件中添加表  
  
1. 在中**服务器资源管理器**，右键单击**表**节点，然后单击**搜索和添加表**。  
  
2. 在中**搜索表名称**文字框中，指定搜索字符串，可以搜索 SAP 系统中的表，然后单击**搜索**。  
  
   > [!NOTE]
   >  [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]支持星号 （*） 通配符字符的使用，以搜索表。  
  
3. **搜索结果**框列出了满足搜索条件的表名。  
  
    ![DDEX 插件&#45;中搜索和添加表名称对话框](../../adapters-and-accelerators/adapter-sap/media/737fc9c3-5258-4693-a2f3-5b5b8d2483e9.gif "737fc9c3-5258-4693-a2f3-5b5b8d2483e9")  
  
4. 选中你想要添加，然后单击的表相对应的复选框**添加**。 若要选择所有表，请单击**全**。 若要清除所有选择，请单击**都清除所有**。  
  
5. 一个对话框通知你刷新后，会导致添加的表可见**表**节点。 单击“确定” 。  
  
6. 右键单击**表**节点，然后选择**刷新**。 所选的表的显示下**表**节点。 单击表名以查看中的表属性**属性**窗格。  
  
7. 展开表名称以查看表的字段。 单击字段名称，请参阅中的字段属性**属性**窗格。  
  
### <a name="to-add-rfcs-from-an-sap-system-using-the-ddex-plug-in"></a>若要从 SAP 系统使用的 DDEX 插件添加 Rfc  
  
1. 在中**服务器资源管理器**，右键单击**函数模块**节点，然后单击**搜索和添加函数模块**。  
  
2. 在中**搜索函数模块**文字框中，指定搜索字符串，可以在 SAP 系统中，搜索函数模块，然后单击**搜索**。  
  
   > [!NOTE]
   >  [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]支持使用星号 （*） 通配符字符的搜索功能模块。  
  
3. **搜索结果**框列出了满足搜索条件的函数模块。  
  
    ![DDEX 插件&#45;在搜索和添加模块对话框](../../adapters-and-accelerators/adapter-sap/media/8c7f9081-80aa-4bfe-8f06-2c751758ddd0.gif "8c7f9081-80aa-4bfe-8f06-2c751758ddd0")  
  
4. 选择你想要添加，然后单击的函数模块到相应的复选框**添加**。 若要选择的所有模块，请单击**全**。 若要清除所有选择，请单击**都清除所有**。  
  
5. 一个对话框通知你刷新后，会导致添加的函数模块可见**函数模块**节点。 单击“确定” 。  
  
6. 右键单击**函数模块**节点，然后选择**刷新**。 所选的函数模块显示下**函数模块**节点。 单击要查看的属性中的函数模块名称**属性**窗格。  
  
7. 展开的函数模块名称，若要查看用于导入、 导出、 更改和表参数节点。  
  
8. 展开**导入**节点以列出函数模块的导入参数。 同样，展开**导出**并**表**节点，以便查看函数模块的导出和表参数的列表。  
  
## <a name="see-also"></a>请参阅  
 [使用 mySAP Business Suite 的 .NET Framework 数据提供程序](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)