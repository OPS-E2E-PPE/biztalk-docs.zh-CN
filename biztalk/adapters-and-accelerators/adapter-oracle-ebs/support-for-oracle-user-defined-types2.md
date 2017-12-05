---
title: "对 Oracle 用户定义 Types2 支持 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d4b9980-fa5b-4340-a62f-e4a4f98603dc
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f38b7ea3c811912e40a5ed3dc0b47df5b8aa884f
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="support-for-oracle-user-defined-types"></a>对 Oracle 用户定义类型的支持
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]包含 Oracle User-Defined 类型 (Udt) 的支持 Oracle E-business Suite 和基础数据库中执行对项目的操作。 Udt 可出现在以下项目：  
  
-   接口的表和包含 UDT 列的界面视图。  
  
-   数据库表和视图包含 UDT 列。  
  
-   包、 存储的过程和函数包含 UDT 参数。  
  
## <a name="what-is-an-oracle-udt"></a>什么是 Oracle UDT？  
 Oracle Udt 帮助中的复杂实体表示为"单个"对象，可以在应用程序之间共享。 例如，它是到模型实际实体，如"客户"或"销售订单"可能的 Oracle 数据库中的对象。 Oracle Udt 定义在 Oracle 数据库中，并且它们为以下两种类型：  
  
-   对象类型。 例如，Oracle 对象。  
  
-   集合类型。 例如，嵌套的表类型或 VARRAY。  
  
 Oracle UDT 的名称区分大小写，并且必须指定方式如下: [SCHEMA_NAME]。[UDT_NAME]。  
  
## <a name="how-does-the-adapter-support-oracle-udt"></a>适配器如何支持 Oracle UDT？  
 ODP.NET 支持通过表示在 Oracle 数据库中定义为.NET 类型 （自定义类型） 的 Oracle Udt 的 Udt。 自定义类型的.NET 成员定义的 Oracle UDT 属性或元素之间的映射。 自定义类型可以是.NET 类或结构，并且可以表示 Oracle 对象或 Oracle 集合。  由于这一事实， [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ODP.NET 用于连接到 Oracle 数据库时，它将继承对 Oracle Udt 的支持。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ODP.NET 用于指定自定义类型映射，以将.NET 自定义类型映射到数据库中 Oracle UDT。 若要指定的自定义类型映射，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用自定义类型工厂。 因此，若要使用 Oracle UDT，程序集 （.dll 文件） 是必需，它定义的自定义类型工厂。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使您能够生成的自定义类型工厂生成包含 Oracle UDT 项目/操作的元数据时的程序集。  
  
> [!NOTE]
>  适配器生成在 ODP.NET 用于支持 Oracle Udt 的类基于 Oracle Udt 的程序集。 有关如何在 ODP.NET 支持 Oracle Udt 的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=140697](http://go.microsoft.com/fwlink/?LinkId=140697)。  
  
 将生成在设计时使用 Oracle Udt 的程序集文件，然后将其用于更高版本在运行时中，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开以下绑定属性：  
  
-   **GeneratedUserTypesAssemblyFilePath** （设计时）  
  
-   **GeneratedUserTypesAssemblyKeyFilePath** （设计时）  
  
-   **UserAssembliesLoadPath** （运行时间）  
  
 有关这些绑定属性的信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
## <a name="performing-operations-on-artifacts-containing-oracle-udts"></a>在包含 Oracle Udt 的项目上执行操作  
 在包含使用的 Udt 的项目上执行操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，必须执行以下操作，在设计时和运行时。  
  
### <a name="design-time"></a>设计时  
 你必须为 Visual Studio 中的操作执行这些步骤时生成架构。  
  
1.  连接到 Oracle E-business Suite 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 有关此操作的信息，请参阅[连接到 Visual Studio 中 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)。  
  
2.  在连接时，在**绑定属性**选项卡**配置适配器**对话框框中，指定为相应值**GeneratedUserTypesAssemblyFilePath**和**GeneratedUserTypesAssemblyKeyFilePath**绑定属性。 有关这些绑定属性的信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
3.  当你连接到 Visual Studio 中的 Oracle E-business Suite 时，浏览到包含 Oracle UDT 的所需项目。 关于浏览项目的信息，请参阅[浏览、 搜索和检索用于 Oracle E-business 操作的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)。  
  
4.  选择所需的项目中，，然后单击**确定**。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]为用户所选的项目中定义的 Oracle 类型生成程序集 （.dll 文件） 以及所选操作的元数据。 在中指定的位置创建程序集**GeneratedUserTypesAssemblyFilePath**绑定属性。  
  
5.  继续执行与用于生成和部署你的项目的步骤的其余部分。  
  
### <a name="run-time"></a>运行时间  
 中的适配器客户端在 Oracle Udt 上执行操作，必须执行这些步骤。  
  
 **BizTalk Server 中**  
  
-   手动添加在步骤 4 中在"设计时"到全局程序集缓存 (GAC) 中您的计算机上创建的 Oracle UDT 程序集。 或者，你可以手动复制 BizTalk Server 安装位置下的 Oracle UDT 程序集。 对于 BizTalk Server 中，通常这是\<安装驱动器\>: files\microsoft BizTalk Server。  
  
-   配置时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]WCF 自定义或 WCF OracleEBS 端口，在**绑定**选项卡上，指定 Oracle UDT 程序集的位置为**UserAssembliesLoadPath**绑定属性。 有关此绑定属性的信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
 **Visual Studio 中**  
  
-   手动添加在步骤 4 中在"设计时"到全局程序集缓存 (GAC) 中您的计算机上创建的 Oracle UDT 程序集。 或者，你可以手动 Oracle UDT 将程序集复制到的项目可执行文件，这通常是在项目的 \bin\Debug 文件夹下的同一位置。  
  
-   指定的 Oracle UDT 程序集的位置**UserAssembliesLoadPath**绑定属性。 有关此绑定属性的信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)