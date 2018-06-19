---
title: 数据提供程序用于与插件 DDEX SAP |Microsoft 文档
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
ms.openlocfilehash: a2a1dd348b6d897e147d6add49499e9716a67aeb
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "25963459"
---
# <a name="use-the-data-provider-for-sap-with-the-ddex-plug-in"></a>数据提供程序用于与插件 DDEX SAP
如果你选择安装[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]连同[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装，安装程序将安装[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]DDEX 插件。 你可以使用此插件浏览 SAP 对象使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 本部分提供有关使用 DDEX 插件的信息。  
  
 你可以使用插件来建立与 SAP 系统中，连接将表添加从 SAP 系统，并从 SAP 系统中添加函数模块。 已添加的表和函数模块使用 Visual Studio 插件后，新添加的表和函数模块将反映在 SAPDiscoveredObjects.xml 文件中。 有关此文件的详细信息，请参阅[关于 SAPDiscoveredObjects.xml 文件中 SAP](../../adapters-and-accelerators/adapter-sap/about-the-sapdiscoveredobjects-xml-file-in-sap.md)。  
  
## <a name="prerequisites"></a>必要條件  
 请确保您选择要安装[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]连同[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装。  
  
### <a name="to-connect-to-an-sap-system-using-the-ddex-plug-in"></a>若要连接到 SAP 系统使用 DDEX 插件  
  
1.  启动 Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
2.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]上**视图**菜单上，单击**服务器资源管理器**。  
  
3.  在**服务器资源管理器**，右键单击**数据连接**，然后选择**添加连接**。  
  
4.  在**更改数据源**对话框中，从**数据源**框中，选择**\<其他\>**。  
  
5.  从**数据提供程序**下拉列表中，选择**mySAP Business Suite 的.NET Framework 数据提供程序**单击**确定**。 **添加连接**对话框随即打开。  
  
6.  **添加连接**对话框将列出要连接到 SAP 系统的不同的连接参数。 一个典型的连接字符串以连接到 SAP 系统使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]需要：  
  
    -   连接类型的连接参数。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]支持连接类型 A、 B 和 d。若要连接到 SAP 系统必须提供连接参数任何*一个*的这些连接类型。 例如，对于 A 的连接类型，必须提供应用程序服务器主机和系统编号的名称。  
  
    -   要连接到 SAP 系统如用户名和密码的登录信息。  
  
     有关连接字符串以连接到 SAP 系统使用的详细信息[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[SAP 连接字符串中读取有关数据提供程序类型](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)。  
  
     在**添加连接**对话框框中，指定：  
  
    -   连接类型的参数的任何一个连接。  
  
    -   要连接到 SAP 系统的登录信息。  
  
    -   是否想要启用 SAP GUI 调试。  
  
    -   是否想要使用 RFC SDK 跟踪。  
  
     单击 **“确定”**。 下创建新的连接节点**数据连接**与上一步中指定的服务器名称的节点。  
  
7.  展开新的连接节点，可以查看**表**和**函数模块**节点。  
  
     建立连接后下, 图显示服务器资源管理器。  
  
     ![DDEX 即插即用&#45;中 SAP ADO.NET 提供程序](../../adapters-and-accelerators/adapter-sap/media/158afc11-9c90-4333-bc62-5901f8d0c794.gif "158afc11-9c90-4333-bc62-5901f8d0c794")  
  
### <a name="to-add-tables-from-an-sap-system-using-the-ddex-plug-in"></a>若要从使用插件 DDEX SAP 系统中添加表  
  
1.  在**服务器资源管理器**，右键单击**表**节点，然后单击**搜索和添加表**。  
  
2.  在**搜索表名称**文本框中，指定搜索字符串来搜索表中的 SAP 系统，并单击**搜索**。  
  
    > [!NOTE]
    >  [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]支持仅星号 （*） 通配符字符的使用，以搜索表。  
  
3.  **搜索结果**框中列出的满足搜索条件的表名称。  
  
     ![DDEX 即插即用&#45;中搜索和添加表名称对话框](../../adapters-and-accelerators/adapter-sap/media/737fc9c3-5258-4693-a2f3-5b5b8d2483e9.gif "737fc9c3-5258-4693-a2f3-5b5b8d2483e9")  
  
4.  选中对应于你想要添加，然后单击表的复选框**添加**。 若要选择所有表，请单击**都选择所有**。 若要清除所有选择，请单击**都清除所有**。  
  
5.  对话框框，通知你，你在刷新后，添加的表将是可见**表**节点。 单击 **“确定”**。  
  
6.  右键单击**表**节点，然后选择**刷新**。 所选的表下显示**表**节点。 单击某个表名称以查看中的表属性**属性**窗格。  
  
7.  展开表名以查看字段的表。 单击字段名称，请参阅中的字段属性**属性**窗格。  
  
### <a name="to-add-rfcs-from-an-sap-system-using-the-ddex-plug-in"></a>若要使用插件 DDEX 某个 SAP 系统从添加 Rfc  
  
1.  在**服务器资源管理器**，右键单击**函数模块**节点，然后单击**搜索和添加函数模块**。  
  
2.  在**搜索函数模块**文本框中，指定搜索字符串来搜索函数模块中 SAP 系统，并单击**搜索**。  
  
    > [!NOTE]
    >  [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]支持仅星号 （*） 通配符字符的使用的搜索功能的模块。  
  
3.  **搜索结果**框列出了满足搜索条件的函数模块。  
  
     ![DDEX 即插即用&#45;中搜索和添加模块对话框](../../adapters-and-accelerators/adapter-sap/media/8c7f9081-80aa-4bfe-8f06-2c751758ddd0.gif "8c7f9081-80aa-4bfe-8f06-2c751758ddd0")  
  
4.  选中你想要添加，然后单击函数模块所对应的复选框**添加**。 若要选择的所有模块，请单击**都选择所有**。 若要清除所有选择，请单击**都清除所有**。  
  
5.  对话框框，通知你，你在刷新后，已将函数添加的模块将是可见**函数模块**节点。 单击 **“确定”**。  
  
6.  右键单击**函数模块**节点，然后选择**刷新**。 所选的函数模块会出现在**函数模块**节点。 单击某个函数模块名称，以查看中的属性**属性**窗格。  
  
7.  展开某个函数模块名称，以查看节点以进行导入、 导出、 更改和表参数。  
  
8.  展开**导入**节点列出函数模块的导入参数。 同样，展开**导出**和**表**节点以查看导出和表函数模块的参数的列表。  
  
## <a name="see-also"></a>另请参阅  
 [使用 mySAP Business Suite 的 .NET Framework 数据提供程序](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)