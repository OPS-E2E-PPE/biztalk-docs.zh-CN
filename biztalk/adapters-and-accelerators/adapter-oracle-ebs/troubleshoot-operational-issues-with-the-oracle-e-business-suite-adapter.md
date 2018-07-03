---
title: 使用 Oracle E-business Suite 适配器进行的操作问题故障排除 |Microsoft Docs
description: 常见的问题和解决方法为 Oracle EBS 适配器在 BizTalk 适配器包 (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 667633e0-055a-418a-ab64-d4f6e6c7a898
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d119afaea2382e1ede6c780a40bbe2bf4329860f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989982"
---
# <a name="troubleshoot-operational-issues-with-the-oracle-e-business-suite-adapter"></a>使用 Oracle E-business Suite 适配器进行的操作问题故障排除
本部分讨论如何使用故障排除技术来解决操作使用时可能遇到的错误[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]。  
  
## <a name="enabling-tracing"></a>启用跟踪  
 有关跟踪中的支持的详细信息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，[诊断跟踪和消息日志记录中的 Oracle E-business Suite 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/diagnostic-tracing-and-message-logging-in-the-oracle-e-business-suite-adapter.md)。  
  
## <a name="known-issues"></a>已知问题  
 以下是在使用时可能遇到的最常见错误[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，以及其可能的原因和解决方法。  
  
  
  
###  <a name="BKMK_LoadBindings"></a> 加载适配器绑定时出错  
 **问题**  
  
 当您尝试启动[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，收到以下错误：  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 **原因**  
  
 当您尝试启动[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，WCF 将加载所有已安装的适配器的适配器绑定。 反过来，适配器绑定都依赖于企业应用程序特定的客户端软件。 您可能会遇到此问题的一个或两个原因如下：  
  
- 在安装该适配器的计算机上未安装所需的 LOB 客户端软件。  
  
- 未将适配器安装中包含的所有适配器的典型或完全安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 但是，可能只有一个企业应用程序安装 LOB 客户端库。 因此，在 GUI 无法加载其他适配器的绑定。  
  
  **解决方法**  
  
- 请确保在您安装的计算机上安装了所需的 LOB 客户端版本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关支持的客户端版本的信息，请参阅安装指南位于\<安装驱动器\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。  
  
- 请确保执行要安装仅需要的适配器的适配器的自定义安装。  
  
###  <a name="BKMK_Display"></a> Oracle E-business Suite 适配器不会显示在 BizTalk Server 管理控制台中的适配器列表中  
 **问题**  
  
 与早期版本附带的适配器的不同[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，则[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]附带[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]中的适配器列表中未显示[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
 **原因**  
  
 最新[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]是 WCF 自定义绑定。 因此，尽管[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中显示[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，它不会显示 WCF 自定义绑定，因此，不会显示基于 WCF 的[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
 **解决方法**  
  
 您可以显式添加[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中所述的步骤[将 Oracle E-business Suite 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)。  
  
###  <a name="BKMK_MissingAction"></a> 执行对 Oracle E-business Suite 操作时出错  
 **问题**  
  
 执行对 Oracle E-business Suite 使用的任何操作时，适配器将报告以下错误[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
- **为 BizTalk Server**  
  
  ```  
  System.ArgumentNullException: Value cannot be null.  
  ```  
  
  **原因**  
  
  未指定消息的 WCF 操作。 WCF 需要用于为每个操作，向适配器通知上的 LOB 应用程序执行的操作指定的 SOAP 操作。  
  
  **解决方法**  
  
  在发送端口或为 BizTalk 业务流程的消息上下文属性指定的 SOAP 操作。 有关说明，请参阅[配置用于 Oracle E-business Suite 的 SOAP 操作](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md)。 请参阅[的消息和消息架构 Oracle EBS 适配器](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)若要查看每个操作的操作的列表。  
  
###  <a name="BKMK_WrongClient"></a> 在接收位置删除请求消息时，BizTalk 进程可能会崩溃由于不正确的 Oracle 客户端版本  
 **问题**  
  
 在 BizTalk 业务流程中定义的接收位置删除请求消息后，业务流程处理的消息和 BizTalk 主机 (BTSNTSvc.exe) 发生崩溃，并重新启动。  
  
 **原因**  
  
 安装 Oracle 客户端将 PATH 变量中添加对最新的客户端程序集的引用。 此外，对最新安装 Oracle 客户端程序集引用在之前对现有客户端程序集的引用。 因此，如果最新的 Oracle 客户端安装，不支持的客户端版本的 BizTalk 主机将崩溃，然后重新启动。  
  
 例如，假定在计算机上已安装支持的 Oracle 客户端 11.1.0.7 和 PATH 变量具有以下引用：  
  
```  
C:\oracle\product\11.1.0\client_1\bin;  
```  
  
 如果同一台计算机上安装的不受支持的 Oracle 客户端，例如 10.2.0.3，，则 PATH 变量将具有以下引用：  
  
```  
C:\oracle\product\10.2.0\db_2\bin;C:\oracle\product\11.1.0\client_1\bin;  
```  
  
 请注意，不受支持的客户端版本引用之前的受支持的版本，因此 BizTalk 主机出现故障。 如果有多个 BizTalk 主机运行，承载适配器出现故障。  
  
 **解决方法**  
  
 如果同一台计算机上安装多个 Oracle 客户端，则请确保在 PATH 变量中的其他 Oracle 客户端版本之前引用的受支持的 Oracle 客户端版本。 例如，如果受支持的 Oracle 客户端版本是 11.1.0.7，PATH 变量中的引用必须如下所示：  
  
```  
  
C:\oracle\product\11.1.0\client_1\bin;C:\oracle\product\10.2.0\db_2\bin;  
```  
  
###  <a name="BKMK_Overflow"></a> 适配器可能引发溢出异常在执行某项操作  
 **问题**  
  
 如果尝试执行包含内部数据集或弱类型化 REF CURSOR 的 Oracle 数值数据类型的操作，请使用适配器，适配器可能引发溢出异常。  
  
 **原因**  
  
 如果提供的数据集或不适合放在相应的.NET 类型的弱类型化 REF CURSOR 的 Oracle 数值数据类型较大的值，将发生这种情况。  
  
 **解决方法**  
  
 如果你想要传递的数据集或弱类型化 REF CURSOR 的 Oracle 数值数据类型的较大值，则必须启用安全设置的值键入**EnableSafeTyping**属性绑定到**true**. 启用安全键入以字符串形式公开的数据集或弱类型化 REF CURSOR 的 Oracle 数值数据类型。  
  
###  <a name="BKMK_Arithmetic"></a> 适配器可能引发算术溢出异常在执行 ExecuteScalar 操作  
 **问题**  
  
 如果尝试执行 SELECT 语句中检索大量的 ExecuteScalar 操作，请使用该适配器，适配器将引发以下异常:"System.OverflowException： 算术运算导致溢出。"  
  
 **原因**  
  
 发生这种情况中 ODP.NET ExecuteScalar 操作的已知限制。 ODP.NET 尝试为.NET Decimal 数据类型，数据中容纳不下并且如果结果太大，.NET Decimal 类型中容纳不下，引发异常。  
  
 **解决方法**  
  
 ExecuteScalar 操作中的 SELECT 语句中使用 TO_CHAR() 转换作为字符串返回的数据。  
  
###  <a name="BKMK_AppContext"></a> 适配器客户端可能会引发以下异常执行某项操作:"无法检索用户 id、 责任 id、 应用程序 id。检查在是否传递了正确的值。"  
 **问题**  
  
 如果您正在执行对 Oracle E-business Suite 项目 （接口表、 界面视图、 并发程序和请求集） 的操作，适配器客户端可能会引发此异常。  
  
 **原因**  
  
 如果提供了对界面表、 界面视图、 并发程序和请求集执行操作时不正确的 Oracle 用户名、 密码和责任名称组合，将发生这种情况。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]需要这些值才能设置这些项目的应用程序上下文。 有关设置应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
 **解决方法**  
  
 必须指定正确的 Oracle 用户名、 密码和负责适当地设置某一 Oracle E-business Suite 项目的应用程序上下文组合。 若要指定的 Oracle 用户名和密码值，必须使用**OracleUserName**并**OraclePassword**绑定属性。 若要为 Oracle 责任指定值，您可以使用**OracleEBSResponsibilityName**绑定属性或消息上下文属性。  
  
###  <a name="BKMK_RootNode"></a> 使用 BizTalk 项目中的 RootNode TypeName 错误  
 **问题**  
  
 中的 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，则从架构生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]包含无效的字符或保留的字**RootNode TypeName**属性，编译项目时将发生以下错误:  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 **解决方法**  
  
1.  右键单击该错误，然后选择中引用的 rood 这样节点**属性**。  
  
2.  有关**RootNode TypeName**属性，删除任何非法字符或保留字，例如，点 （.）。  
  
###  <a name="BKMK_InvalidBinding"></a> 无效的绑定时出现的警告在 Visual Studio 中使用适配器  
 **问题**  
  
 当您使用适配器中创建应用程序[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]和打开由适配器生成的配置文件 (app.config)，会看到类似于以下警告：  
  
```  
The element 'bindings' has invalid child element 'oracleEBSBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 **原因**  
  
 会出现此警告[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]绑定， `oracleEBSBinding`，不标准绑定随附于[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。  
  
 **解决方法**  
  
 可以安全地忽略此警告。  
  
###  <a name="BKMK_Notify"></a> BizTalk Server 将引发异常，如果在同一个应用程序中使用多个通知架构或在同一主机上的多个应用程序中使用通知架构  
 **问题**  
  
 BizTalk Server 将引发异常，表明该应用程序找不到文档规范，因为多个架构匹配的消息类型或 XLANG 异常。  
  
 **原因**  
  
 由于以下任一发生这种情况：  
  
- 已生成多个通知架构在 BizTalk Server 项目中，将其部署到 BizTalk Server 应用程序，然后运行应用程序从 Oracle 数据库接收通知。 由于通知架构都是公用的冲突之间没有 BizTalk Server 应用程序中部署的架构。  
  
- 发生多个项目时您已为每个 BizTalk Server 部署的项目，每个项目到同一主机上单独的 BizTalk Server 应用程序生成的通知架构，然后运行应用程序或应用程序以接收来自通知Oracle 数据库中。 因为架构和程序集都是可访问 BizTalk Server 中的应用程序，则冲突之间常见的架构部署在各种 BizTalk Server 应用程序和程序集。  
  
  **解决方法**  
  
  为 BizTalk Server 应用程序使用单个通知架构文件。 如果需要在同一主机上的多个 BizTalk Server 应用程序中使用通知架构，创建包含单个通知架构的应用程序，然后使用 BizTalk Server 中的从所有其他应用程序的通知架构。  
  
###  <a name="BKMK_Timeout"></a> 浏览 Oracle E-business Suite 项目在 Visual Studio 中的同时超时异常  
 **问题**  
  
 浏览 Oracle E-business Suite 中的项目的同时[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]使用的项目[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]， [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]可能会遇到超时异常。  
  
 **原因**  
  
 如果承载 Oracle E-business Suite 的服务器速度较慢、 服务器位于远程位置，或要查找在该架构具有大量的项目，则可能发生此错误。  
  
 **解决方法**  
  
 您可以选择增加的价值**SendTimeout**绑定属性或提供的搜索表达式**类别中的搜索**文本框中，以减少项目数的适配器检索。  
  
 有关指定绑定属性的详细信息，请参阅[适用于 Oracle E-business Suite 中配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)。 有关 Oracle E-business Suite 中搜索项目的详细信息，请参阅[浏览、 搜索和获取元数据用于 Oracle E-business Suite 操作](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)。  
  
###  <a name="BKMK_MemUsage"></a> 内存使用情况和线程数将增加时在事务处理的入站操作中使用适配器  
 **问题**  
  
 在事务处理的入站操作中，如轮询，**如果没有数据轮询表中可用**并且该适配器将继续轮询，一段时间内遇到内存使用情况和线程计数的增加。  
  
 **原因**  
  
 **如果没有数据轮询表中可用**后，每个接收超时周期[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]产生了一个新的线程无法继续轮询操作。 因此，一段时间内会增加线程计数和内存使用情况。 但是，如果正在轮询一次的表具有一些数据，同一个线程继续执行所有后续轮询。  
  
 **解决方法**  
  
 我们建议设置**ReceiveTimeout**的最大可能值，这是 24.20:31:23.6470000 （24 天），以便生成新线程，仅每隔 24 天。 这将确保，内存使用情况和线程计数不会不会变得太多时间太短。  
  
 有关详细信息**ReceiveTimeout**绑定属性，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。 指定绑定属性的说明，请参阅[适用于 Oracle E-business Suite 中配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)。  
  
> [!NOTE]
>  使用的适配器时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，超时值设置为较大的值不会影响适配器的功能。  
  
## <a name="see-also"></a>请参阅  
[Oracle EBS 适配器故障排除](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)