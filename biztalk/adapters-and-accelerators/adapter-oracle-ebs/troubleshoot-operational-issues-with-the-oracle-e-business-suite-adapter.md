---
title: "与 Oracle E-business Suite 适配器排除操作问题 |Microsoft 文档"
description: "常见的问题和 Oracle EBS 适配器 BizTalk 适配器包 (BAP) 中的解决方法"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 667633e0-055a-418a-ab64-d4f6e6c7a898
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4654e228a4ca86c9d89686f826d57777f2353efd
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="troubleshoot-operational-issues-with-the-oracle-e-business-suite-adapter"></a>与 Oracle E-business Suite 适配器排除操作问题
本部分讨论如何使用故障排除方法来解决操作使用时可能遇到的错误[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]。  
  
## <a name="enabling-tracing"></a>启用跟踪  
 有关跟踪中的支持的详细信息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，[诊断跟踪和消息日志记录中的 Oracle E-business Suite 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/diagnostic-tracing-and-message-logging-in-the-oracle-e-business-suite-adapter.md)。  
  
## <a name="known-issues"></a>已知问题  
 以下是使用时可能遇到的最常见错误[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，以及其可能的原因和解决方法。  
  
  
  
###  <a name="BKMK_LoadBindings"></a>在加载适配器绑定错误  
 **问题**  
  
 当你尝试启动[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，你将收到以下错误：  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 **可能的原因**  
  
 当你尝试启动[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，WCF 加载所有已安装适配器的适配器绑定。 反过来，适配器绑定都依赖于企业应用程序的特定客户端软件。 你可能会遇到此问题的一个或两个原因如下：  
  
-   在安装适配器的计算机上未安装所需的 LOB 客户端软件。  
  
-   未将适配器安装中包含的所有适配器的典型或完全安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 但是，可能只有一个企业应用程序安装 LOB 客户端库。 因此，GUI 无法加载其他适配器的绑定。  
  
 **解决方法**  
  
-   请确保在你安装的计算机上安装了所需的 LOB 客户端版本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关支持的客户端版本的信息，请参阅安装指南位于\<安装驱动器\>: files\microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。  
  
-   请确保执行适配器安装需要适配器的自定义安装。  
  
###  <a name="BKMK_Display"></a>Oracle E-business Suite 适配器不会显示在列表中在 BizTalk Server 管理控制台中的适配器  
 **问题**  
  
 与不同的是较早版本附带的适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]附带[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]未显示在列表中中适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
 **可能的原因**  
  
 最新[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]是 WCF 自定义绑定。 因此，尽管[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台显示[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，它不会显示 WCF 自定义绑定，并因此，不会显示基于 WCF 的[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
 **解决方法**  
  
 你可以显式添加[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中所述的步骤[将 Oracle E-business Suite 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)。  
  
###  <a name="BKMK_MissingAction"></a>执行对 Oracle E-business Suite 操作时出错  
 **问题**  
  
 适配器执行针对 Oracle E-business Suite 使用的任何操作时将报告以下错误[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
-   **BizTalk server**  
  
    ```  
    System.ArgumentNullException: Value cannot be null.  
    ```  
  
 **可能的原因**  
  
 未指定消息的 WCF 操作。 WCF 需要为每个操作，在 LOB 应用程序上执行的操作会告知适配器指定的 SOAP 操作。  
  
 **解决方法**  
  
 指定的 SOAP 操作中发送端口或 BizTalk 业务流程中的消息上下文属性。 有关说明，请参阅[配置用于 Oracle E-business Suite 的 SOAP 操作](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md)。 请参阅[消息和 Oracle EBS 适配器的消息架构](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)若要查看的每个操作的操作的列表。  
  
###  <a name="BKMK_WrongClient"></a>当在接收位置除去请求消息时，BizTalk 进程可能会崩溃由于不正确的 Oracle 客户端版本  
 **问题**  
  
 在 BizTalk 业务流程中定义接收位置删除请求消息后，业务流程使用该消息并 BizTalk 主机 (BTSNTSvc.exe) 发生崩溃并重新启动。  
  
 **可能的原因**  
  
 安装 Oracle 客户端在 PATH 变量中添加对最新的客户端程序集的引用。 此外，对最新安装 Oracle 客户端程序集的引用位于之前对现有客户端程序集的引用。 因此，如果最新的 Oracle 客户端安装不支持的客户端版本的中，BizTalk 主机发生崩溃，，然后重新启动。  
  
 例如，假定在计算机上已安装支持的 Oracle 客户端 11.1.0.7 和 PATH 变量具有以下引用：  
  
```  
C:\oracle\product\11.1.0\client_1\bin;  
```  
  
 如果不支持的 Oracle 客户端，例如 10.2.0.3，安装在同一台计算机上，路径变量将拥有以下引用：  
  
```  
C:\oracle\product\10.2.0\db_2\bin;C:\oracle\product\11.1.0\client_1\bin;  
```  
  
 请注意，不受支持的客户端版本引用之前的受支持的版本，因此 BizTalk 主机发生崩溃。 如果有多个 BizTalk 主机运行，承载适配器崩溃。  
  
 **解决方法**  
  
 如果同一台计算机上安装多个 Oracle 客户端，请确保在 PATH 变量中的其他 Oracle 客户端版本之前引用的受支持的 Oracle 客户端版本。 例如，如果支持的 Oracle 客户端版本，11.1.0.7 PATH 变量中的引用必须如下所示：  
  
```  
  
C:\oracle\product\11.1.0\client_1\bin;C:\oracle\product\10.2.0\db_2\bin;  
```  
  
###  <a name="BKMK_Overflow"></a>适配器可能引发上执行运算溢出异常  
 **问题**  
  
 如果你尝试执行操作包含在数据集或弱类型 REF CURSOR 的 Oracle 数值数据类型，请使用该适配器，该适配器可能引发溢出异常。  
  
 **可能的原因**  
  
 如果你提供在数据集或弱类型 REF CURSOR，无法容纳到相应的.NET 类型内的 Oracle 数值数据类型为较大的值，将发生这种情况。  
  
 **解决方法**  
  
 如果你想要将较大的值传递的数据集或弱类型 REF CURSOR 内的 Oracle 数值数据类型，则必须启用安全设置的值键入**EnableSafeTyping**属性绑定到**true**. 启用安全键入将在数据集或弱类型 REF CURSOR 内的 Oracle 数值数据类型公开为字符串。  
  
###  <a name="BKMK_Arithmetic"></a>适配器可能会引发执行 ExecuteScalar 操作出现算术溢出异常  
 **问题**  
  
 使用适配器，如果你尝试在检索大量的 ExecuteScalar 操作中执行 SELECT 语句，该适配器将引发以下异常:"System.OverflowException： 算术运算导致溢出。"  
  
 **可能的原因**  
  
 由于在 ODP.NET ExecuteScalar 操作的已知限制发生这种情况。 ODP.NET 尝试进行转换的.NET 十进制数据类型，数据中容纳不下，并且如果结果为太大，.NET 十进制类型中容纳不下，将引发异常。  
  
 **解决方法**  
  
 使用 ExecuteScalar 操作中的 SELECT 语句中 TO_CHAR() 将转换为字符串返回的数据。  
  
###  <a name="BKMK_AppContext"></a>适配器客户端可能会引发以下异常上执行操作:"无法检索用户 id、 责任 id、 应用程序 id。检查中是否传递了正确的值。"  
 **问题**  
  
 如果您正在执行对 Oracle E-business Suite 项目 （接口表、 界面视图、 并发程序和请求集） 的操作，适配器客户端可能会引发此异常。  
  
 **可能的原因**  
  
 如果提供了对接口表、 界面视图、 并发程序和请求集执行操作时不正确的 Oracle 用户名、 密码和责任名称组合，将发生这种情况。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]需要这些值才能设置这些项目的应用程序上下文。 有关设置应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
 **解决方法**  
  
 你必须指定正确的 Oracle 用户名、 密码和适当设置 Oracle E-business Suite 项目的应用程序上下文有责任组合。 若要指定的 Oracle 用户名和密码的值，必须使用**OracleUserName**和**OraclePassword**绑定属性。 若要指定值的 Oracle 责任，则您可以使用**OracleEBSResponsibilityName**绑定属性或消息上下文属性。  
  
###  <a name="BKMK_RootNode"></a>与 RootNode TypeName BizTalk 项目中的错误  
 **问题**  
  
 在 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，如果从架构生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]包含无效字符或保留的字**RootNode TypeName**属性，编译项目时将出现以下错误:  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 **解决方法**  
  
1.  右键单击该错误并选择中引用的 rood 节点**属性**。  
  
2.  有关**RootNode TypeName**属性，删除任何非法字符或保留字，例如，圆点 （.）。  
  
###  <a name="BKMK_InvalidBinding"></a>使用 Visual Studio 中的适配器时出现的无效的绑定警告  
 **问题**  
  
 当你使用该适配器创建的应用程序在[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]并打开生成的适配器的配置文件 (app.config)，你看到类似于以下警告：  
  
```  
The element 'bindings' has invalid child element 'oracleEBSBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 **可能的原因**  
  
 由于会出现此警告[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]绑定， `oracleEBSBinding`，不标准绑定随[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。  
  
 **解决方法**  
  
 可以安全地忽略此警告。  
  
###  <a name="BKMK_Notify"></a>BizTalk Server 引发异常，如果你在同一应用程序使用多个通知架构或跨同一个主机上的多个应用程序使用通知架构  
 **问题**  
  
 BizTalk Server 引发 XLANG 异常或异常指出应用程序找不到文档规范，因为多个架构匹配的消息类型。  
  
 **可能的原因**  
  
 由于以下任一发生这种情况：  
  
-   在你生成多个通知架构在 BizTalk Server 项目中，将其部署到 BizTalk Server 应用程序，，然后运行应用程序从 Oracle 数据库接收通知。 由于通知架构是公用的冲突之间没有部署 BizTalk Server 应用程序中的架构。  
  
-   发生多个项目，你已为每个 BizTalk 服务器到单独的 BizTalk Server 应用程序在同一主机上的每个项目部署的项目生成通知架构，然后运行应用程序或应用程序接收来自通知Oracle 数据库中。 因为架构和程序集都可访问 BizTalk Server 中的应用程序，各种 BizTalk Server 应用程序和程序集下部署的常见架构之间存在不冲突。  
  
 **解决方法**  
  
 BizTalk Server 应用程序使用单个通知架构文件。 如果你需要在同一主机上的多个 BizTalk Server 应用程序中使用通知架构，创建包含单个通知架构的应用程序，然后使用 BizTalk Server 中的所有其他应用程序中的通知架构。  
  
###  <a name="BKMK_Timeout"></a>浏览 Visual Studio 中的 Oracle E-business Suite 项目时的超时异常  
 **问题**  
  
 浏览 Oracle E-business Suite 项目中的同时[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]项目使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]， [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]可能会遇到超时异常。  
  
 **可能的原因**  
  
 如果承载 Oracle E-business Suite 的服务器速度缓慢、 服务器位于远程位置，或您要查找下的架构具有大量的项目，则可能发生这种情况。  
  
 **解决方法**  
  
 你可以选择的值增加**SendTimeout**绑定属性或提供搜索表达式中的**类别中的搜索**文本框中，以减少的项目数，该适配器检索。  
  
 有关指定绑定属性的详细信息，请参阅[为 Oracle E-business Suite 配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)。 有关在 Oracle E-business Suite 中搜索项目的详细信息，请参阅[浏览、 搜索和 get 元数据用于 Oracle E-business Suite 操作](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)。  
  
###  <a name="BKMK_MemUsage"></a>内存使用情况和线程计数的增加而在事务处理的入站操作中使用该适配器时  
 **问题**  
  
 在事务处理的入站操作中，如轮询，**如果没有数据轮询表中可用**和适配器继续轮询，通过一段时间则会遇到内存使用量和线程计数的增加。  
  
 **可能的原因**  
  
 **如果没有数据轮询表中可用**之后，每个接收超时周期[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]生成新的线程来继续轮询操作。 因此，通过一段时间会增加线程计数和内存使用情况。 但是，如果正在轮询一次的表具有一些数据，同一个线程继续执行所有后续的轮询。  
  
 **解决方法**  
  
 我们建议设置**ReceiveTimeout**为最大可能值，这是 24.20:31:23.6470000 （24 天），以便生成新线程，仅每隔 24 天。 这将确保，内存使用情况和线程计数不会增长过多时间太短。  
  
 有关详细信息**ReceiveTimeout**绑定属性，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。 指定绑定属性的说明，请参阅[为 Oracle E-business Suite 配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)。  
  
> [!NOTE]
>  使用的适配器时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，将超时设置为较大的值不会影响的适配器的功能。  
  
## <a name="see-also"></a>另请参阅  
[故障排除 Oracle EBS 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)