---
title: 业务流程管理解决方案的文件清单 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, file inventory
ms.assetid: 3efb7495-9543-4fe0-8f4b-26c19b3b6db9
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4cc187a96e7252fad7edacba10b7a3dcc39c1b33
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973867"
---
# <a name="file-inventory-for-the-business-process-management-solution"></a>业务流程管理解决方案的文件清单
本部分列出了业务流程管理解决方案的子目录和源文件。 业务流程管理解决方案源文件的默认安装目录为 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios\BPM。 下表将具有此路径之前的说明\<安装 Directory\>。  
  
 中的文件\<安装目录\>  
  
|文件|Description|  
|----------|-----------------|  
|Microsoft.Samples.BizTalk.SouthridgeVideo.sln|Visual Studio 解决方案文件。|  
|readme.html|解决方案的自述文件。|  
|ReplacePKToken.vbs|构建解决方案时用于修复解决方案文件中公钥标记的 VBScript。|  
|ReplacePKToken.wsf|ReplacePKToken VBScript 的 Windows 脚本文件。|  
|SetupBPM.bat|创建公钥，更新指向公钥的引用和编译解决方案。 有关部署解决方案的信息，请参阅[部署业务流程管理解决方案](../core/deploying-the-business-process-management-solution.md)。|  
  
 中的文件\<安装目录\>\BAM  
  
|文件|Description|  
|----------|-----------------|  
|BAMServiceOrder.xls|BAM 数据的 Excel 电子表格。|  
|BAMServiceOrder.xml|定义 BAM 数据项类型的架构。|  
  
 中的文件\<安装目录\>\Bindings  
  
|文件|Description|  
|----------|-----------------|  
|CableOrderAppBindings-test.xml|测试版本的绑定文件**CableOrderApp**应用程序。|  
|CableOrderAppBindings.xml|绑定文件**CableOrderAPP**应用程序。|  
|MessagingAppBindings-test.xml|测试版本的绑定文件**MessagingApp**应用程序。|  
|MessagingAppBindings.xml|绑定文件**MessagingApp**应用程序。|  
|OrderBrokerAppBindings-test.xml|测试版本的绑定文件**OrderBrokerApp**应用程序。|  
|OrderBrokerAppBindings.xml|绑定文件**OrderBrokerApp**应用程序。|  
  
 中的文件\<安装目录\>\CableProvisioningSystemClient  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|模拟订单系统的组件客户端的程序集文件。|  
|CableProvisioningSystemClient.csproj|C# 项目文件。|  
|CPSClient.cs|客户端的源。 包括**OrderHandlerWrapper**类代码。|  
|OrderException.cs|C# 类定义文件**OrderException**。|  
  
 中的文件\<安装目录\>\CableProvisioningSystemServer  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|模拟订单系统的组件服务器端的程序集文件。|  
|CableProvisioningSystemServer.csproj|C# 项目文件。|  
|CableProvisioningSystemServer.csproj.user|Visual Studio 项目用户选项文件|  
|CPSServer.cs|服务器的源。|  
  
 中的文件\<安装目录\>\CSRWebApp  
  
|文件|Description|  
|----------|-----------------|  
|CSRMainForm.aspx|客户服务输入 ASP 窗体。|  
|CSRMainForm.aspx.cs|C# 代码隐藏窗体。|  
|Web.Config|窗体的配置文件。|  
  
 中的文件\<安装目录\>\CSRWebApp\App_WebReferences\SouthridgeVideo_OrderBroker  
  
|文件|Description|  
|----------|-----------------|  
|orderbrokerorch_orderport.disco|Disco 文件**OrderBroker**显示为 web 服务。|  
|orderbrokerorch_orderport.discomap|生成的文件。|  
|orderbrokerorch_orderport.wsdl|WSDL 文件的**OrderBroker**显示为 web 服务。|  
  
 中的文件\<安装目录\>\FacilitiesSimulator  
  
|文件|Description|  
|----------|-----------------|  
|FacilitiesSimulator.csproj|功能模拟程序的 C# 项目文件。|  
|FacilitiesSimulator.csproj.user|Visual Studio 项目用户选项文件|  
|FacilitiesSimulatorForm.cs|功能模拟程序的 C# 代码。|  
|FacilitiesSimulatorForm.resx|资源文件。|  
  
 中的文件\<安装目录\>\HistoryDB  
  
|文件|Description|  
|----------|-----------------|  
|CreateDatabase.cmd|用于驱动创建历史记录数据库的 SQL 文件的文件。|  
|SouthridgeVideoHistory.sql|用于创建历史记录数据库的 SQL 命令。|  
  
 中的文件\<安装目录\>\IOperationsSystem  
  
|文件|Description|  
|----------|-----------------|  
|IOperationsSystem.cs|操作系统的接口定义。|  
|IOperationsSystem.csproj|C# 项目文件。|  
|IOperationsSystem.csproj.user|Visual Studio 项目用户选项文件|  
  
 中的文件\<安装目录\>\IOrderHandler  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|IOrderHandler.cs|接口定义**OrderHandler**。|  
|IOrderHandler.csproj|C# 项目文件。|  
  
 中的文件\<安装目录\>\Maps  
  
|文件|Description|  
|----------|-----------------|  
|Maps.btproj|BizTalk 项目文件。|  
|Order_To_SQLUpdateStatus.btm|用于将订单转换为消息以更新状态的映射。|  
  
 中的文件\<安装目录\>\MessagingSchemas  
  
|文件|Description|  
|----------|-----------------|  
|ErrorEnvelope.xsd|定义错误消息的信封的架构。|  
|MessagingSchemas.btproj|BizTalk 项目文件。|  
|OrderEnvelope.xsd|定义订单的信封的架构。|  
|OrderStatusEnvelope.xsd|定义订单状态消息的信封的架构。|  
|SQLUpdateStatus.xsd|定义 SQL 状态更新消息的信封的架构。|  
  
 中的文件\<安装目录\>\OperationsClient  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|OperationsClient.csproj|操作客户端的 C# 项目。|  
|OpsClient.cs|操作客户端的 C# 代码。|  
|OpsExceptions.cs|定义操作异常的 C# 代码。|  
  
 中的文件\<安装目录\>\OperationsHandler  
  
|文件|Description|  
|----------|-----------------|  
|OperationsHandler.csproj|操作处理程序的 C# 项目文件。|  
|OpsHandler.cs|C# 代码中的为**OpsHandler**。 使用**OpsClient**发出请求的操作系统。|  
  
 中的文件\<安装目录\>\OperationsServer  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|OperationsServer.csproj|操作服务器的 C# 项目文件。|  
|OpsServer.cs|C# 代码中为提供的实例的操作服务器**OpsHandler**对象。|  
  
 中的文件\<安装目录\>\OpsAdapter  
  
|文件|Description|  
|----------|-----------------|  
|OpsAdapter.sln|Ops 适配器的 Visual Studio 解决方案。|  
|Register_Ops_Adapter.vbs|用于注册 Ops 适配器的 VBScript。|  
|SetupOpsAdapter.bat|用于安装 Ops 适配器的批处理文件。|  
  
 中的文件\<安装目录\>\OpsAdapter\IOpsAIC  
  
|文件|Description|  
|----------|-----------------|  
|IOpsAIC.cs|用于接口定义的 C# 代码文件**初始化**和**执行**Ops 适配器由调用的方法。|  
|IOpsAIC.csproj|C# 项目文件。|  
  
 中的文件\<安装目录\>\OpsAdapter\OpsAdapterMgmt  
  
|文件|Description|  
|----------|-----------------|  
|AdapterManagement.cs|Ops 适配器的 C# 源文件。|  
|AssemblyInfo.cs|程序集信息文件。|  
|OpsAdapterMgmt.csproj|Ops 适配器的 C# 源文件。|  
|TransmitHandler.xsd|Ops 适配器的 C# 源文件。|  
|TransmitLocation.xsd|Ops 适配器的 C# 源文件。|  
  
 中的文件\<安装目录\>\OpsAdapter\OpsTxAdapter  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|OpsAdapterExceptions.cs|Ops 适配器的 C# 源文件。|  
|OpsAdapterProperties.cs|Ops 适配器的 C# 源文件。|  
|OpsTransmitAdapterBatch.cs|Ops 适配器的 C# 源文件。|  
|OpsTransmitter.cs|Ops 适配器的 C# 源文件。|  
|OpsTxAdapter.csproj|C# 项目文件。|  
  
 中的文件\<安装目录\>\Orchestrations\CableOrderActions  
  
|文件|Description|  
|----------|-----------------|  
|Activate.odx|**激活**订单处理阶段所使用的业务流程。|  
|Analyze.odx|**分析**订单处理阶段所使用的业务流程。|  
|CableOrderActions.btproj|BizTalk 项目文件。|  
|Cancel.odx|**取消**订单处理阶段所使用的业务流程。|  
|Change.odx|**更改**订单处理阶段所使用的业务流程。|  
|Complete.odx|**完成**订单处理阶段所使用的业务流程。|  
|Validate.odx|**验证**订单处理阶段所使用的业务流程。|  
  
 中的文件\<安装目录\>\Orchestrations\CableOrderStage1  
  
|文件|Description|  
|----------|-----------------|  
|CableOrder1.odx|第一个订单处理阶段的业务流程。|  
|CableOrderStage1.btproj|BizTalk 项目文件。|  
  
 中的文件\<安装目录\>\Orchestrations\CableOrderStage2  
  
|文件|Description|  
|----------|-----------------|  
|CableOrder2.odx|第二个订单处理阶段的业务流程。|  
|CableOrderStage2.btproj|BizTalk 项目文件。|  
  
 中的文件\<安装目录\>\Orchestrations\OrderBroker  
  
|文件|Description|  
|----------|-----------------|  
|OrderBroker.btproj|BizTalk 项目文件。|  
|OrderBroker.odx|**OrderBroker**业务流程。|  
  
 中的文件\<安装目录\>\Orchestrations\OrderManager  
  
|文件|Description|  
|----------|-----------------|  
|CheckInterrupt.odx|**CheckInterrupt**业务流程。|  
|ErrorHandler.odx|**ErrorHandler**业务流程。|  
|ExceptionHandler.odx|**ExceptionHandler**业务流程。|  
|Interrupter.odx|**Interrupter**业务流程。|  
|OrderManager.btproj|BizTalk 项目文件。|  
|OrderManager.odx|**OrderManager**业务流程。|  
  
 中的文件\<安装目录\>\OrderBrokerMaps  
  
|文件|Description|  
|----------|-----------------|  
|CSR_OrderRequest_To_Order.btm|用于将客户服务订单请求转换为订单消息的映射。|  
|CSR_OrderRequest_To_Servicing_OrderRequest.btm|用于将客户服务订单请求转换为服务消息的映射|  
|CSR_OrderRequest_To_SQLHistoryInsert.btm|用于将客户服务订单请求转换为历史记录更新消息的映射。|  
|OrderBrokerMaps.btproj|BizTalk 项目文件。|  
|Order_To_CSR_OrderRequest.btm|用于将订单消息转换为客户服务订单请求的映射。|  
  
 中的文件\<安装目录\>\OrderBrokerSchemas  
  
|文件|Description|  
|----------|-----------------|  
|CSR_OrderRequest.xsd|客户服务请求的架构。|  
|OrderBrokerSchemas.btproj|BizTalk 项目文件。|  
|Servicing_OrderRequest.xsd|定义发送到服务系统的消息的架构。|  
|SQLHistoryInsert.xsd|SQL 历史记录消息的架构。|  
  
 中的文件\<安装目录\>\OrderBroker_Proxy  
  
|文件|Description|  
|----------|-----------------|  
|Global.asax|生成的文件。|  
|Index.htm|生成的文件。|  
|OrderBrokerOrch_OrderPort.asmx|生成的文件。|  
|Web.config|生成的文件。|  
  
 中的文件\<安装目录\>\OrderBroker_Proxy\App_Code  
  
|文件|Description|  
|----------|-----------------|  
|DataTypes.cs|生成的文件。|  
|OrderBrokerOrch_OrderPort.asmx.cs|生成的文件。|  
  
 中的文件\<安装目录\>\OrderHandler  
  
|文件|Description|  
|----------|-----------------|  
|OrderHandler.cs|C# 代码中的为**OrderHandler**对象。|  
|OrderHandler.csproj|C# 项目文件。|  
  
 中的文件\<安装目录\>\Rules  
  
|文件|Description|  
|----------|-----------------|  
|DecodeAndValidateOrderRules.xml|业务规则引擎的规则文件。|  
  
 中的文件\<安装目录\>\SampleMessages  
  
|文件|Description|  
|----------|-----------------|  
|CSR_OrderRequest.xml|示例客户服务订单请求。|  
|OrderEnvelope.xml|示例订单信封。|  
  
 中的文件\<安装目录\>\SchemaClasses  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|InternalMessages.cs|定义用于在解决方案的各组件之间进行通信的消息的类的 C# 代码。|  
|SchemaClasses.csproj|C# 项目文件。|  
  
 中的文件\<安装目录\>\Schemas  
  
|文件|Description|  
|----------|-----------------|  
|Order.xsd|订单消息的架构。|  
|OrderPropertySchema.xsd|订单消息的升级属性架构。|  
|Schemas.btproj|BizTalk 项目文件。|  
  
 中的文件\<安装目录\>\Scripts  
  
|文件|Description|  
|----------|-----------------|  
|CleanDirs.cmd|要删除文件仅执行测试版本的解决方案的结合使用的目录的命令文件。|  
|CreateAppReferences.vbs|VBScript 以创建应用程序的引用。|  
|CreateQueues.vbs|VBScript 以创建 MSMQ 队列。|  
|CreateSouthridgeVideoApplication.cmd|要在 SSO 配置存储区中创建的配置值的命令文件。|  
|CreateTestDirectories.cmd|要创建的测试新版解决方案的目录的命令文件。|  
|DeployBPM.cmd|要将解决方案部署的命令文件。|  
|regac.bat|要在全局程序集缓存 (GAC) 中注册程序集的批处理文件。|  
|SouthridgeVideoSSOConfiguration.xml|包含的初始的 SSO 配置值的文件。|  
  
 中的文件\<安装目录\>\ServiceLevelTracking  
  
|文件|Description|  
|----------|-----------------|  
|Activity_CustomerOrderRequest.cs|C# 代码以定义客户订单请求 BAM 活动。|  
|Activity_OrderManager.cs|C# 代码以定义顺序 manager BAM 活动。|  
|Activity_ServiceOrderRequest.cs|C# 代码来定义服务顺序请求 BAM 活动。|  
|ServiceLevelTracking.cs|C# 代码以定义活动的抽象基类。|  
|ServiceLevelTracking.csproj|C# 项目文件。|  
  
 中的文件\<安装目录\>\Utilities  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|CableOrderException.cs|C# 代码定义电缆 order 异常类。|  
|Helper.cs|各种助手类和方法的 C# 代码。|  
|Recaller.cs|C# 代码中的为**Recaller**对象。|  
|SSOConfigHelper.cs|C# 代码的 SSO 配置帮助程序对象和方法。|  
|Utilities.csproj|C# 项目文件。|  
  
## <a name="see-also"></a>另请参阅  
 [业务流程管理解决方案参考](../core/business-process-management-solution-reference.md)   
 [业务流程管理解决方案的组件](../core/components-of-the-business-process-management-solution.md)