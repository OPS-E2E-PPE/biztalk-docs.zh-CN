---
title: Oracle E-business Suite 适配器常见问题 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4f7fe4e0-ddd5-402f-bbbc-b320850eaf3b
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d576fa5dae04a43daa54f2d99e7f9c14d1341e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218053"
---
# <a name="oracle-e-business-suite-adapter-faqs"></a>Oracle E-business Suite 适配器常见问题
以下一些常见问题 (Faq) 与相关[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]。 另请参阅[BizTalk 适配器包常见问题](../../adapters-and-accelerators/frequently-asked-questions-for-the-biztalk-adapter-pack.md)。
  

## <a name="how-can-i-use-the-oracle-e-business-adapter-to-communicate-with-oracle-e-business-suite"></a>如何使用 Oracle E-business 适配器与 Oracle E-business Suite 通信？  
 你可以使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与 Oracle E-business Suite 应通过开发 BizTalk 应用程序，使用 WCF 服务模型或使用 WCF 通道模型进行通信。 有关详细信息，请参阅[概述的 BizTalk Adapter for Oracle E-business Suite](http://msdn.microsoft.com/library/4f18fa2e-4e97-4c28-b38d-fc39ac53789e)。  
  
## <a name="what-interfaces-are-supported-by-the-oracle-e-business-adapter-for-retrieving-metadata"></a>为检索元数据的 Oracle E-business 适配器支持哪些接口？  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]为检索元数据支持两个接口：  
  
-   MetadataExchange WCF 提供的。 WCF 提供了元数据交换终结点的所有 WCF 绑定，它使客户端从 Oracle E-business Suite 获取元数据。  
  
-   IMetadataRetrievalContract 由 WCF LOB 适配器 SDK 的说明进行操作，它支持浏览和搜索功能的适配器的元数据。  
  
## <a name="how-does-the-adapter-connect-to-oracle-e-business-suite"></a>适配器如何连接到 Oracle E-business Suite？  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]个 Oracle 客户端使用 Oracle 数据访问组件。 [支持 LOB 系统](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)列出客户端版本。 若要连接到 Oracle E-business Suite，适配器客户端必须提供连接字符串，[连接统一资源标识符 (URI)](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)。 在内部，该适配器将连接 URI 映射到要连接到 Oracle E-business Suite 中的基础数据库的连接字符串。 请参阅[创建连接到 Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)。  
  
## <a name="does-the-oracle-e-business-adapter-provide-a-secure-way-of-communicating-with-the-oracle-e-business-suite--are-there-any-best-practices-to-ensure-data-security"></a>Oracle E-business 适配器是否提供与 Oracle E-business Suite 进行通信的安全的方法？  是否有任何最佳实践，以确保数据安全？  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]上建立与 Oracle E-business Suite 的连接进行身份验证支持企业单一登录 (SSO)。 SSO 使用数据库和主密钥进行加密和存储用户凭据。 它还提供服务，以 Microsoft Windows 帐户映射到用于访问后端系统的辅助凭据。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]还要求你输入用户名和密码以连接到 Oracle E-business Suite 的凭据。 这些凭据用于身份验证用户，并因此提供的连接的授权级别。 Oracle E-business 适配器提供了多种方法可以通过其提供这些凭据。 有关如何安全地提供 BizTalk 解决方案中的 Oracle 凭据的信息，请参阅[适配器与 BizTalk Server 的安全](../../adapters-and-accelerators/adapter-oracle-ebs/security-with-the-oracle-e-business-suite-adapter-and-biztalk-server.md)。 有关如何安全地提供编程解决方案中的 Oracle 凭据的信息，请参阅[安全使用 Oracle EBS 适配器编程](../../adapters-and-accelerators/adapter-oracle-ebs/secure-programming-with-the-oracle-ebs-adapter.md)。  
  
 详细信息：  
  
-   中的数据安全性[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[保护 Oracle EBS 应用程序](../../adapters-and-accelerators/adapter-oracle-ebs/secure-your-oracle-ebs-applications.md)。  
  
-   最佳做法，以确保中的数据安全性[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[最佳安全方案](../../adapters-and-accelerators/adapter-oracle-ebs/best-practices-to-secure-the-oracle-e-business-suite-adapter.md)。  
  
## <a name="is-there-a-gui-provided-by-the-oracle-e-business-adapter-to-view-and-perform-operations-on-the-artifacts-in-oracle-e-business-suite"></a>是否有由 Oracle E-business 适配器提供一个 GUI，以查看和 Oracle E-business Suite 中执行操作的项目？  
 使用适配器服务 BizTalk 项目外接程序和添加适配器服务引用 Visual Studio 插件提供一个对话框，你可以在其中查看和 Oracle E-business Suite 中执行操作的项目。 有关 GUI 提供的详细信息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[浏览、 搜索和 get 元数据的 Oracle EBS 操作](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)。  
  
## <a name="what-are-binding-properties-in-the-oracle-e-business-adapter-where-can-i-find-information-about-all-the-binding-properties-in-the-oracle-e-business-adapter"></a>什么 Oracle E-business 适配器中的绑定属性？ 在哪里 Oracle E-business 适配器中找到有关绑定的所有属性的信息？  
 适配器客户端可以使用中的绑定属性[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]来配置和控制适配器的行为。 有关绑定的所有属性的信息显示在[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[使用的绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
## <a name="what-are-inbound-and-outbound-operations-in-the-oracle-e-business-adapter"></a>Oracle E-business 适配器中的入站和出站操作有哪些？  
 在入站操作中，LOB 系统 (Oracle E-business Suite) 是客户端并且适配器客户端服务，其中事务源自 Oracle E-business Suite。 例如，在轮询和通知操作。  
  
 在出站操作中，适配器客户端客户端并且 LOB 系统 (Oracle E-business Suite) 会变为的服务，其中事务源自适配器客户端。 例如，Insert、 选择、 更新和删除操作接口表、 存储的过程和函数，对操作和复合操作。  
  
## <a name="where-can-i-find-information-about-the-oracle-data-types-that-are-supported-in-the-oracle-e-business-adapter"></a>在哪里可以找到有关 Oracle E-business 适配器中支持的 Oracle 数据类型的信息？  
 有关支持中的 Oracle 数据类型信息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[基本 Oracle 数据类型](../../adapters-and-accelerators/adapter-oracle-ebs/basic-oracle-data-types2.md)。  
  
## <a name="what-is-applications-context-how-can-i-set-applications-context-for-various-oracle-artifacts-in-the-oracle-e-business-adapter"></a>什么是应用程序上下文？ 如何在 Oracle E-business 适配器中设置各种 Oracle 项目的应用程序上下文？  
 有关应用程序上下文和如何在中设置信息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
## <a name="which-approach-biztalk-server-wcf-service-model-or-wcf-channel-model-can-i-use-to-perform-various-operations-using-the-oracle-e-business-adapter"></a>我可使用哪种方法 （BizTalk Server、 WCF 服务模型或 WCF 通道模型） 来执行各种操作使用 Oracle E-business 适配器？  
 有关这种方法可用于执行各种操作使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[开发应用程序 Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)。  
  
## <a name="see-also"></a>另请参阅  
[BizTalk 适配器包的常见问题](../../adapters-and-accelerators/frequently-asked-questions-for-the-biztalk-adapter-pack.md)