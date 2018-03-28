---
title: 设置应用程序上下文 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9697155-70c0-4173-80d2-d02d103c397b
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88db982be92123a13084892bfc396cb1d89c46ac
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="set-application-context"></a>设置应用程序上下文
在[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]，你可以对其执行操作之前某些 Oracle E-business Suite 项目 （接口表、 界面视图、 并发程序和请求集） 的强制设置应用程序上下文。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不允许你执行这些项目上的操作，直到你安装的应用程序上下文。 但是，对于基础的 Oracle 数据库中的项目，它是由用户是否要设置为应用程序上下文。  
  
## <a name="what-is-application-context"></a>什么是应用程序上下文  
 应用程序上下文是一套与 Oracle E-business Suite 实现用户首选项和项目的访问控制中的项目关联的元素。 应用程序上下文由以下元素组成：  
  
-   **用户名称**： 用户可以连接到 Oracle E-business Suite。  
  
-   **责任**： 职责是在 Oracle E-business Suite，用户可访问这些数据和函数，适合于组织中其角色的访问级别。 职责可以允许访问特定应用程序，操作系统单元、 组书籍和 windows、 函数和其他责任的限制的列表。 通过分配给用户的职责，你可以授予/限制访问的 Oracle E-business Suite 中的用户。  
  
-   **组织 ID**: Oracle E-business Suite 支持最大的多个组织的设置。 这些不同的组织中的值来，组织 ID 中存储有关这些组织的信息的 Oracle E-business Suite 的表的 Org_ID 列唯一标识。 通过将分配到组织责任或显式选择组织，你可以授予/限制访问用户的组织。  
  
 有关责任的详细信息，多个组织和 Oracle E-business Suite 中的组织 ID 搜索[Oracle 帮助中心](http://docs.oracle.com)。  
  
## <a name="setting-application-context"></a>设置应用程序上下文  
 作为[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]为未建立或在适配器中初始化 Oracle E-business Suite 项目连接到 Oracle E-business Suite，应用程序上下文中的基础数据库。 你可以初始化，或设置在这些项目的应用程序上下文[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]通过使用下列操作之一：  
  
-   **绑定属性**:[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开以下绑定属性用于设置应用程序上下文： **OracleEBSOrganizationId**， **OracleUserName**， **OraclePassword**， **OracleEBSResponsibilityKey**， **OracleEBSResponsibilityName**，和**ApplicationShortName**。 不需要指定所有这些绑定属性，若要设置的各种项目的应用程序上下文的值。 有关所需的项目的设置应用程序上下文的绑定属性的信息，请参阅[绑定属性的设置应用程序上下文的各种项目](#Binding)本主题中更高版本。  
  
-   **消息上下文属性**:[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开以下消息上下文属性用于设置应用程序上下文： **ApplicationShortName**，**组织 Id****ResponsibilityKey**，和**ResponsibilityName**。 对于指定的用户名和密码，必须使用的绑定属性。 有关如何设置使用消息上下文属性的应用程序上下文的信息，请参阅[配置应用程序上下文使用消息上下文属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md)。  
  
> [!IMPORTANT]
>  为指定的值**OracleEBSResponsibilityKey**绑定属性将重写的值**OracleEBSResponsibilityName**绑定属性。 同样，为指定的值**ResponsibilityKey**消息上下文属性将为指定的值重写**ResponsibilityName**消息上下文属性。  
  
### <a name="precedence-order-binding-properties-vs-message-context-properties"></a>优先顺序 （与消息上下文属性的绑定属性）  
 如果设置使用的绑定属性和消息上下文属性的应用程序上下文，指定消息上下文属性的值将优先，并替代的绑定属性为指定的值。 但是，例如，如果为消息上下文属性和其他人绑定属性中指定的应用程序的短名称，仅应用程序短名称的值执行从消息上下文属性并且其余选取从相关的绑定属性。  
  
 **应用程序短名称的优先顺序**  
  
 设置应用程序上下文，时的应用程序的短名称采用以下优先顺序 （从高到低）：  
  
-   中指定的应用程序短名称**ApplicationShortName**消息上下文属性。  
  
-   （对于接口表、 界面视图、 并发程序和请求仅设置） 的 SOAP 操作中指定的应用程序短名称。  
  
-   中指定的应用程序短名称**ApplicationShortName**绑定属性。  
  
 但是，对于接口表、 界面视图、 并发程序和请求集中，此优先级顺序是仅适用时设置的应用程序上下文。 若要标识接口表、 界面视图，并发程序和请求设置，使用的 SOAP 操作中的短名称的应用程序。  
  
 **优先顺序为责任密钥和责任名称**  
  
 设置应用程序上下文，时按以下优先顺序 （从最高到最低） 使用的责任密钥和责任名称：  
  
-   中指定的责任密钥**ResponsibilityKey**消息上下文属性。  
  
-   中指定的责任名称**ResponsibilityName**消息上下文属性。  
  
-   中指定的责任密钥**OracleEBSResponsibilityKey**绑定属性。  
  
-   中指定的责任名称**OracleEBSResponsibilityName**绑定属性。  
  
> [!TIP]
>  **为何使用通过绑定属性设置的应用程序上下文的消息上下文属性？** 如果你设置使用绑定属性的应用程序上下文，WCF 自定义发送端口为 Oracle E-business 适配器可以仅用于进行特定的组织 ID、 职责范围以及为绑定属性指定的应用程序。 相反，如果你使用的消息上下文属性可以配置"泛型"的 WCF 自定义发送端口，并在消息级别设置的应用程序上下文。  
  
### <a name="setting-application-context-for-interface-tables-interface-views-concurrent-programs-and-request-sets-mandatory"></a>设置应用程序上下文接口表、 界面视图、 并发程序和请求集 （必需）  
 对接口表、 界面视图、 并发程序执行操作之前，必须设置应用程序上下文中的和请求集[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 若要执行此操作，必须提供的绑定属性或消息上下文属性之前指定相应的值。  
  
> [!IMPORTANT]
>  你不能对表执行操作接口，界面视图、 并发程序和请求设置除非上下文属性设置为所需的绑定属性或消息的相应值。  
  
### <a name="setting-application-context-for-plsql-apis-procedures-functions-tables-and-views"></a>PL/SQL Api、 过程、 函数、 表和视图的设置应用程序上下文  
  
-   **PL/SQL Api**:[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开与 Oracle 数据库，以及 Oracle E-business Suite 应用程序关联的 PL/SQL Api。 可选设置与 Oracle 数据库相关联的 PL/SQL api 的应用程序上下文时，它是必需的设置与 Oracle E-business Suite 应用程序关联的 PL/SQL api 的应用程序上下文。  
  
-   **过程和函数**： 并不一定要设置用于 Oracle 数据库中执行操作的过程和函数的应用程序上下文。  
  
-   **表和视图**： 并不一定要设置要执行的 Oracle 数据库中的表和视图上的操作的应用程序上下文。 但是，对于自定义的 Oracle E-business Suite 应用程序，用户可能或可能不为接口表进行注册的基数据库表。 如果未作为接口表注册数据库表，它将显示中的数据库表以及[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 因为这些表与 Oracle 电子商务应用程序关联，必须在这些表上的任何操作设置应用程序上下文。  
  
 若要设置这些项目的应用程序上下文，必须为绑定属性或消息上下文属性之前指定提供适当的值。  
  
### <a name="setting-application-context-for-poll-executenonquery-executereader-executescalar-and-composite-operations"></a>轮询、 ExecuteNonQuery、 ExecuteReader、 ExecuteScalar 和复合操作的设置应用程序上下文  
 除了项目，你还可以设置在这些项目执行的各种操作的应用程序上下文。  
  
-   若要设置轮询操作的应用程序上下文，你可以只使用的绑定属性指定更早版本。 有关设置应用程序上下文，你必须为适用于在其执行轮询操作的项目的绑定属性提供适当的值。 例如，如果接口表上执行轮询操作，则你必须指定接口表绑定属性的值。  
  
-   若要设置的 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作的应用程序上下文，你必须提供相应的值的绑定属性或消息之前指定的上下文属性。 有关这些操作的设置应用程序上下文，你必须提供相应的值的绑定属性或消息上下文属性适用于在其执行的操作的项目。  
  
-   若要设置复合操作的应用程序上下文，必须为绑定属性或消息上下文属性之前指定提供适当的值。 对于复合操作的设置应用程序上下文，你必须提供相应的值的绑定属性或消息上下文属性适用于对各个操作。 例如，如果复合操作包含两个操作： 一个在接口表上，在数据库上的其他表然后，你必须指定的绑定属性或接口表，以及绑定的消息上下文属性的值属性或数据库表的消息上下文属性。  
  
    > [!IMPORTANT]
    >  对于所有这些操作，它是一定要设置的应用程序上下文，如果对 Oracle E-business Suite （接口表、 接口视图、 并发程序或请求集） 中的项目执行此操作。 如果基础数据库中的项目上执行该操作，则不一定要设置的应用程序上下文。 例如，如果您正在执行接口表上的轮询操作，则一定要设置的应用程序上下文，而如果对表执行轮询操作，则不一定要设置的应用程序上下文。  
  
## <a name="setting-the-language-for-performing-operations"></a>设置执行操作的语言  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持 Oracle E-business Suite 的多语言支持 (MLS) 功能，允许你在执行操作时指定一种语言。 适配器公开**语言**绑定下的属性**MlsSettings**绑定属性和**语言**消息上下文属性指定的语言执行操作。  
  
 为指定的值**语言**消息上下文属性将重写的值**语言**绑定下的属性**MlsSettings**绑定属性。 有关详细信息**MlsSettings**绑定属性，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
##  <a name="Binding"></a> 对于各种项目设置应用程序上下文的绑定属性  
 下表提供了有关必须为其指定适当的值设置的各种项目的应用程序上下文的绑定属性的信息：  
  
|项目|OracleEBSOrganizationId|OracleUserName|OraclePassword|OracleEBSResponsibilityKey<br />或<br />OracleEBSResponsibilityName|ApplicationShortName|  
|---|---|---|---|---|---|  
|接口表和接口视图|√*|√|√|√||  
|并发程序|√*|√|√|√||  
|请求集|√*|√|√|√||  
|PL/SQL Api|√*|√|√|√|√|  
|过程和功能|√*|√|√|√|√|  
|表和视图|√*|√|√|√|√|  
  
 **√\* = 可选**  
  
> [!IMPORTANT]
>  -   默认值**OracleEBSOrganizationId**绑定属性 （可选） 为 null。 如果指定的值**OracleEBSOrganizationId**绑定属性，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]在设置应用程序上下文时，将会话的 ORG_ID 设置为此值。  
> -   为指定的值**OracleEBSResponsibilityKey**绑定属性重写为指定的值**OracleEBSResponsibilityName**绑定属性。  
  
 有关上述每个绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)