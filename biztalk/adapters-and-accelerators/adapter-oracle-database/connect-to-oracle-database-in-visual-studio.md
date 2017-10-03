---
title: "连接到 Visual Studio 中的 Oracle 数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 766264c8-bb3f-49e9-b851-1022d1fa5076
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1c0bd45e311a2d6b56fdda9560a1c0300bb711b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-oracle-database-in-visual-studio"></a>连接到 Visual Studio 中的 Oracle 数据库
如何使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  

## <a name="connection-options-in-visual-studio"></a>Visual Studio 中的连接选项

使用时[!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]，有几个选项可供连接到 Oracle 数据库。 这些选项包括： 

-    **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** 位于[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目。 你使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]若要为你想要针对 BizTalk 解决方案中的操作生成消息架构 (Xsd)。 有关使用 BizTalk Server 开发解决方案的详细信息，请参阅[开发 BizTalk 应用程序使用 Oracle 数据库适配器](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md)。  
  
-    **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** 位于[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目。 你使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]若要为你想要针对 BizTalk 解决方案中的操作生成消息架构 (Xsd)。 有关使用 BizTalk Server 开发解决方案的详细信息，请参阅[开发 BizTalk 应用程序使用 Oracle 数据库适配器](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md)。  
  
    > [!NOTE]
    >  因为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]公开 WCF 自定义绑定，而且作为 BizTalk 适配器，你可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]从 BizTalk 项目连接到 SQL Server。  
  
-    **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** 在非 BizTalk 编程项目中可用。 你使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成 WCF 客户端类或 WCF 服务回调接口，当你开发使用 WCF 服务模型的解决方案时。 有关开发与 WCF 服务模型的解决方案的详细信息，请参阅[开发 Oracle 数据库应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)。  
  
 若要使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，您必须首先连接到 Oracle 数据库。 所有三个方法所显示的对话框中，你可以通过它来配置通过设置以下连接：  
  
-   **连接参数**。 这些是用于生成连接 URI 的参数。 必须指定数据源 （Oracle net 服务名称）。  
  
-   **用于 Oracle 数据库用户名密码凭据**。 这些凭据用于进行时进行身份验证你对 Oracle 数据库建立连接。 必须指定用户名和密码。  
  
-   **绑定属性**。 生成操作的元数据时，绑定属性是在设计时，即，可选的。 有关绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。  
  
 在最低限度上，配置到 Oracle 数据库中，连接时你只需指定绑定属性和连接参数，需要以建立连接并影响返回的元数据[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]操作你想要针对。 但是，你还可能想要指定用于任何其他绑定属性并将在运行时使用的连接参数的值。 这是因为：  
  
-   [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]从绑定属性和在配置连接时指定的连接参数创建 BizTalk 端口绑定文件并将此文件添加到你的项目。 更高版本，你可以使用此绑定文件以创建在端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关绑定文件的详细信息，请参阅[配置使用端口绑定文件到 Oracle 数据库的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)。  
  
-   [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]从的绑定属性和连接属性时配置该连接，指定创建 app.config 文件并将此文件添加项目目录中。  
  

  
## <a name="see-also"></a>另请参阅  
[获取 Visual Studio 中的 Oracle 数据库操作的元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)