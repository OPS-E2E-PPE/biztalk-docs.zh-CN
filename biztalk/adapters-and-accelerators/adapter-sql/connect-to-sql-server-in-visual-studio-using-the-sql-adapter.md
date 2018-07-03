---
title: 连接到 Visual Studio 中使用 SQL 适配器中的 SQL Server |Microsoft Docs
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
ms.openlocfilehash: 22e527714bb1cf14531a6565cd7987531a4eb07b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014502"
---
# <a name="connect-to-sql-server-in-visual-studio-using-the-sql-adapter"></a>连接到 SQL Server 在 Visual Studio 中使用 SQL 适配器
本部分提供有关如何使用说明[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
- **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** 现已推出[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目并作为的一部分安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。 您使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]为想要面向您的 BizTalk 解决方案中的操作生成消息架构 (Xsd)。 有关使用 BizTalk Server 开发解决方案的详细信息，请参阅[使用 SQL 适配器开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)。  
  
- **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** 现已推出[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目并作为的一部分安装[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装。 您使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]为想要面向您的 BizTalk 解决方案中的操作生成消息架构 (Xsd)。 有关使用开发解决方案的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[使用 SQL 适配器开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)。  
  
  > [!NOTE]
  >  因为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公开为 WCF 自定义绑定和 BizTalk 适配器，可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]从要连接到 SQL Server 的 BizTalk 项目。  
  
- **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** 是在非 BizTalk 编程项目中可用。 您使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]开发使用 WCF 服务模型的解决方案时生成 WCF 客户端类或 WCF 服务回调接口。 有关使用 WCF 服务模型开发解决方案的详细信息，请参阅[开发 SAP 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)。  
  
  若要使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，您必须首先连接到 SQL Server。 所有三个方法所显示的对话框，您可以通过它来配置通过设置以下连接：  
  
- **连接参数**。 这些是用于生成连接 URI，例如 SQL Server 名称、 数据库实例名称和数据库名称的参数。  
  
- **SQL Server 的用户名密码凭据**。 这些用于身份验证对 SQL Server 建立连接。 必须指定用户名和密码。  
  
- **绑定属性**。 绑定属性是可选的并指定它们是否主要取决于是否面向需要设置特定的绑定属性的操作。 有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
  在最低限度上，配置与 SQL Server 的连接时你只需指定绑定属性和连接参数，需要建立连接并会影响返回的元数据的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]到所需的操作目标。 但是，您还可能想要指定任何其他绑定属性和连接参数，将在运行时使用的值。 这是因为：  
  
- [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]从绑定属性和连接参数，指定当配置连接并将此文件添加到你的项目创建的 BizTalk 端口绑定文件。  
  
- [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]创建 app.config 文件中的绑定属性和指定当配置连接并在项目目录中添加此文件的连接属性。  
  
