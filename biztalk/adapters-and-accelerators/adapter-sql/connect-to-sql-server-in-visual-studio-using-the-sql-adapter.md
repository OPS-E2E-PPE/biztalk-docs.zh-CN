---
title: 连接到使用 SQL 适配器的 Visual Studio 中的 SQL Server |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62fc2c01-6e4d-4b3b-8581-1d57436ef4e9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb5e2d149c9a9533e4bec3c2c1c435bffb3adf26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222805"
---
# <a name="connect-to-sql-server-in-visual-studio-using-the-sql-adapter"></a>连接到使用 SQL 适配器的 Visual Studio 中的 SQL Server
本部分提供有关如何使用说明[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
-    **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** 位于[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目并作为的一部分安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。 你使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]若要为你想要针对 BizTalk 解决方案中的操作生成消息架构 (Xsd)。 有关使用 BizTalk Server 开发解决方案的详细信息，请参阅[开发 BizTalk 应用程序使用的 SQL 适配器](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)。  
  
-    **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** 位于[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目并作为的一部分安装[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装。 你使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]若要为你想要针对 BizTalk 解决方案中的操作生成消息架构 (Xsd)。 有关开发解决方案的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[开发 BizTalk 应用程序使用的 SQL 适配器](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)。  
  
    > [!NOTE]
    >  因为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公开 WCF 自定义绑定，而且作为 BizTalk 适配器，你可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]从 BizTalk 项目连接到 SQL Server。  
  
-    **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** 在非 BizTalk 编程项目中可用。 你使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成 WCF 客户端类或 WCF 服务回调接口，当你开发使用 WCF 服务模型的解决方案时。 有关开发与 WCF 服务模型的解决方案的详细信息，请参阅[开发 SAP 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)。  
  
 若要使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，您必须首先连接到 SQL Server。 所有三个方法所显示的对话框中，你可以通过它来配置通过设置以下连接：  
  
-   **连接参数**。 这些是用于生成连接 URI，例如 SQL Server 名称、 数据库实例名称和数据库名称的参数。  
  
-   **SQL Server 的用户名密码凭据**。 这些凭据用于进行时进行身份验证你在 SQL Server 上建立的连接。 必须指定用户名和密码。  
  
-   **绑定属性**。 绑定属性是可选的并且是否指定主要取决于是否面向需要特定绑定来设置属性的操作。 有关绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
 在最低限度上，配置与 SQL Server 的连接时你只需指定绑定属性和连接参数，需要以建立连接并影响返回的元数据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]到所需的操作目标。 但是，你还可能想要指定用于任何其他绑定属性并将在运行时使用的连接参数的值。 这是因为：  
  
-   [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]从绑定属性和连接参数，指定你配置的连接并将此文件添加到你的项目中创建 BizTalk 端口绑定文件。  
  
-   [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]从的绑定属性和连接属性指定当你配置的连接并将此文件添加项目目录中创建的 app.config 文件。  
  
