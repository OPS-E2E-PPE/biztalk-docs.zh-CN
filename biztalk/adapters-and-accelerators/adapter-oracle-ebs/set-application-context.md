---
title: 设置应用程序上下文 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9697155-70c0-4173-80d2-d02d103c397b
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 539983840f07160ad58ec688eda24286dc1a3abc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374573"
---
# <a name="set-application-context"></a>设置应用程序上下文
在[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]，设置应用程序上下文是所必需的 （接口表、 界面视图、 并发程序和请求集） 的某些 Oracle E-business Suite 项目之前您可以对其执行操作。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不允许你在设置应用程序上下文之前执行这些项目上的操作。 但是，对于基础的 Oracle 数据库中的项目，是由用户是否要设置应用程序上下文。  
  
## <a name="what-is-application-context"></a>什么是应用程序上下文  
 应用程序上下文是一组与实现用户首选项和相应的项目的访问控制的 Oracle E-business Suite 中的项目相关联的元素。 应用程序上下文包含以下元素：  
  
- **用户名称**:可以连接到 Oracle E-business Suite 用户。  
  
- **责任**:负责在 Oracle E-business Suite，允许用户访问这些数据和函数，适合于组织中其角色的访问级别。 责任可以允许访问特定的应用程序，操作系统单位、 书籍、 组和一个 windows、 函数和其他责任的限制的列表。 由于分配给用户的职责，您可以授予/限制访问的 Oracle E-business Suite 中的用户。  
  
- **组织 ID**:Oracle E-business Suite 支持设置最多家组织。 一个值，组织 ID 中的表中存储有关这些组织的信息的 Oracle E-business Suite 的 Org_ID 列进行唯一标识这些不同的组织。 通过将分配到组织的职责或显式选择组织，你可以授予/限制访问的用户的组织。  
  
  有关职责的详细信息，搜索多个组织和 Oracle E-business Suite 中的组织 ID [Oracle 帮助中心](http://docs.oracle.com)。  
  
## <a name="setting-application-context"></a>设置应用程序上下文  
 作为[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]用于 Oracle E-business Suite 项目未建立或初始化适配器中连接到 Oracle E-business Suite，应用程序上下文中的基础数据库。 你可以初始化，或设置在这些项目的应用程序上下文[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]通过下列操作之一：  
  
- **绑定属性**:[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开以下绑定属性来设置应用程序上下文：**OracleEBSOrganizationId**， **OracleUserName**， **OraclePassword**， **OracleEBSResponsibilityKey**， **OracleEBSResponsibilityName**，并**ApplicationShortName**。 不需要指定所有这些绑定属性，若要设置的各种项目的应用程序上下文的值。 有关所需的某一项目的设置应用程序上下文的绑定属性的信息，请参阅[设置应用程序上下文的各种项目的绑定属性](#Binding)本主题中更高版本。  
  
- **消息上下文属性**:[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开以下消息上下文属性用于设置应用程序上下文：**ApplicationShortName**， **OrganizationID**， **ResponsibilityKey**，并且**ResponsibilityName**。 对于指定的用户名和密码，必须使用的绑定属性。 有关如何设置应用程序上下文中使用消息上下文属性的信息，请参阅[配置应用程序上下文使用消息上下文属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md)。  
  
> [!IMPORTANT]
>  为指定的值**OracleEBSResponsibilityKey**绑定属性将重写的值**OracleEBSResponsibilityName**属性绑定。 同样，为指定的值**ResponsibilityKey**消息上下文属性将为指定的值重写**ResponsibilityName**消息上下文属性。  
  
### <a name="precedence-order-binding-properties-vs-message-context-properties"></a>优先级顺序 （与消息上下文属性的绑定属性）  
 如果将应用程序上下文中使用的绑定属性和消息上下文属性，指定为消息上下文属性的值将优先于和替代的绑定属性指定的值。 但是，如果作为消息上下文属性和其他人绑定属性中指定的应用程序的短名称，例如，仅应用程序的短名称的值来自消息上下文属性和其余部分从相关的绑定中选取属性。  
  
 **应用程序的短名称的优先顺序**  
  
 设置应用程序上下文，时的应用程序的短名称使用按以下优先级顺序 （最高到低）：  
  
- 中指定的应用程序短名称**ApplicationShortName**消息上下文属性。  
  
- （用于接口表、 界面视图、 并发程序和仅请求集） 的 SOAP 操作中指定的应用程序短名称。  
  
- 中指定的应用程序短名称**ApplicationShortName**属性绑定。  
  
  但是，对于接口表、 界面视图、 并发程序和请求集，此优先级顺序才适用设置应用程序上下文时。 若要标识的接口表、 界面视图，并发程序和请求设置，使用短名称中的 SOAP 操作的应用程序。  
  
  **责任密钥和责任名称的优先顺序**  
  
  设置应用程序上下文，时按以下优先级顺序 （最高到低） 使用的责任密钥和责任名称：  
  
- 中指定的责任密钥**ResponsibilityKey**消息上下文属性。  
  
- 中指定的责任名称**ResponsibilityName**消息上下文属性。  
  
- 中指定的责任密钥**OracleEBSResponsibilityKey**属性绑定。  
  
- 中指定的责任名称**OracleEBSResponsibilityName**属性绑定。  
  
> [!TIP]
>  **为什么通过绑定属性来设置应用程序上下文中使用消息上下文属性？** 如果将使用绑定属性的应用程序上下文，WCF 自定义发送端口用于 Oracle E-business 适配器可用于仅特定组织 ID、 职责范围以及为绑定属性指定的应用程序。 相反，如果使用消息上下文属性可以配置"通用"的 WCF 自定义发送端口，并在消息级别设置应用程序上下文。  
  
### <a name="setting-application-context-for-interface-tables-interface-views-concurrent-programs-and-request-sets-mandatory"></a>设置应用程序上下文的接口表、 界面视图、 并发程序和请求集 （必需）  
 对界面表、 界面视图、 并发程序执行操作之前，必须设置应用程序上下文并设置请求[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 若要执行此操作，必须提供相应的值的绑定属性或前面指定的消息上下文属性。  
  
> [!IMPORTANT]
>  您不能对表执行操作接口、 界面视图、 并发程序和请求设置除非已设置相应的值所需的绑定属性或消息上下文属性。  
  
### <a name="setting-application-context-for-plsql-apis-procedures-functions-tables-and-views"></a>PL/SQL Api、 过程、 函数、 表和视图的设置应用程序上下文  
  
- **PL/SQL Api**:[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开 PL/SQL Api 与 Oracle 数据库，以及 Oracle E-business Suite 应用程序相关联。 可选应用程序上下文设置 PL/SQL api 与 Oracle 数据库相关联时，它是必须为与 Oracle E-business Suite 应用程序关联的 PL/SQL Api 设置应用程序上下文。  
  
- **过程和函数**:不一定要设置应用程序上下文的 Oracle 数据库中执行操作过程和函数。  
  
- **表和视图**:不一定要设置要在 Oracle 数据库中执行对表和视图的操作的应用程序上下文。 但是，对于自定义 Oracle E-business Suite 应用程序，用户可能会或可能无法注册接口表为基础数据库表。 如果数据库表未注册为接口表，它将显示中的数据库表以及[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 由于这些表与相关联的 Oracle 电子商务应用程序，必须对这些表的任何操作的设置应用程序上下文。  
  
  若要设置这些项目的应用程序上下文，必须为绑定属性或前面指定的消息上下文属性提供相应的值。  
  
### <a name="setting-application-context-for-poll-executenonquery-executereader-executescalar-and-composite-operations"></a>设置轮询、 ExecuteNonQuery、 ExecuteReader、 ExecuteScalar 和复合操作的应用程序上下文  
 除了这些项目中，您还可以设置这些项目执行各种操作的应用程序上下文。  
  
-   若要设置轮询操作的应用程序上下文，您可以仅使用的绑定属性指定前面。 有关设置应用程序的上下文，必须为适用于在其执行轮询操作的项目的绑定属性来提供适当的值。 例如，如果在界面表执行轮询操作，然后必须指定的接口表的绑定属性的值。  
  
-   若要设置的 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作的应用程序上下文，您必须提供适当的值的绑定属性或消息前面指定的上下文属性。 有关这些操作的设置应用程序上下文，必须提供适当的值的绑定属性或消息上下文属性适用于在其执行的操作的项目。  
  
-   若要设置复合操作的应用程序上下文，必须为绑定属性或前面指定的消息上下文属性提供相应的值。 复合操作的设置应用程序上下文，必须提供适当的值的绑定属性或消息上下文属性适用于各个操作。 例如，如果复合操作包含两个操作： 一组在界面表，另一种针对数据库表则必须指定的绑定属性或接口表，以及绑定的消息上下文属性的值属性或数据库表的消息上下文属性。  
  
    > [!IMPORTANT]
    >  对于所有这些操作，它是强制性 （接口表、 界面视图、 并发程序或请求集） 的 Oracle E-business Suite 中的某个项目执行此操作将应用程序上下文。 如果基础数据库中的某个项目执行此操作，则不一定要设置应用程序上下文。 例如，如果您正在执行的接口表上的轮询操作，是必须设置应用程序上下文，而如果对表执行轮询操作，则不一定要设置应用程序上下文。  
  
## <a name="setting-the-language-for-performing-operations"></a>设置用于执行操作的语言  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持 Oracle E-business Suite 的多语言支持 (MLS) 功能，并允许您执行操作时指定的语言。 该适配器公开**语言**下的属性绑定**MlsSettings**属性绑定并**语言**消息上下文属性来为指定的语言执行操作。  
  
 为指定的值**语言**消息上下文属性将重写的值**语言**下的属性绑定**MlsSettings**属性绑定。 有关详细信息**MlsSettings**绑定属性，请参阅[了解适用于 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
##  <a name="Binding"></a> 设置的各种项目的应用程序上下文的绑定属性  
 下表提供了有关必须为其指定适当的值以设置各种项目的应用程序上下文的绑定属性的信息：  
  
|项目|OracleEBSOrganizationId|OracleUserName|OraclePassword|OracleEBSResponsibilityKey<br />或<br />OracleEBSResponsibilityName|ApplicationShortName|  
|---|---|---|---|---|---|  
|界面表和界面视图|√*|√|√|√||  
|并发程序|√*|√|√|√||  
|请求集|√*|√|√|√||  
|PL/SQL Api|√*|√|√|√|√|  
|过程和功能|√*|√|√|√|√|  
|表和视图|√*|√|√|√|√|  
  
 **√\* = 可选**  
  
> [!IMPORTANT]
> - 默认值**OracleEBSOrganizationId**绑定属性 （可选） 为 null。 如果指定的值**OracleEBSOrganizationId**属性，绑定[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]设置应用程序上下文时将会话的 ORG_ID 设置为此值。  
>   -   为指定的值**OracleEBSResponsibilityKey**绑定属性将为指定的值重写**OracleEBSResponsibilityName**属性绑定。  
  
 有关每个绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)