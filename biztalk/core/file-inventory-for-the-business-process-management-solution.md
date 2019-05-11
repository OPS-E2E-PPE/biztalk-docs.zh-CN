---
title: 业务流程管理解决方案的文件清单 |Microsoft Docs
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
ms.openlocfilehash: e2f01ad1c8d0f9cafae6ade68de653f609827353
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388033"
---
# <a name="file-inventory-for-the-business-process-management-solution"></a>业务流程管理解决方案的文件清单
本部分列出了子目录和业务流程管理解决方案的源代码文件。 业务流程管理解决方案源文件的默认安装目录[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios\BPM。 下表来代替此路径与之前的说明\<安装目录\>。  
  
 中的文件\<安装目录\>  
  
|文件|Description|  
|----------|-----------------|  
|Microsoft.Samples.BizTalk.SouthridgeVideo.sln|Visual Studio 解决方案文件。|  
|readme.html|该解决方案的自述文件。|  
|ReplacePKToken.vbs|若要修复解决方案文件中的公钥标记，构建解决方案时的 VBScript。|  
|ReplacePKToken.wsf|ReplacePKToken VBScript 的 Windows 脚本文件。|  
|SetupBPM.bat|创建一个公共密钥、 更新引用的公钥，并编译解决方案。 部署解决方案的信息，请参阅[部署业务流程管理解决方案](../core/deploying-the-business-process-management-solution.md)。|  
  
 中的文件\<安装目录\>\BAM  
  
|文件|Description|  
|----------|-----------------|  
|BAMServiceOrder.xls|BAM 数据的 Excel 电子表格。|  
|BAMServiceOrder.xml|定义 BAM 数据项类型的架构。|  
  
 中的文件\<安装目录\>\Bindings  
  
|文件|Description|  
|----------|-----------------|  
|CableOrderAppBindings-test.xml|绑定文件的测试版本**CableOrderApp**应用程序。|  
|CableOrderAppBindings.xml|绑定文件**CableOrderAPP**应用程序。|  
|MessagingAppBindings-test.xml|绑定文件的测试版本**MessagingApp**应用程序。|  
|MessagingAppBindings.xml|绑定文件**MessagingApp**应用程序。|  
|OrderBrokerAppBindings-test.xml|绑定文件的测试版本**OrderBrokerApp**应用程序。|  
|OrderBrokerAppBindings.xml|绑定文件**OrderBrokerApp**应用程序。|  
  
 中的文件\<安装目录\>\CableProvisioningSystemClient  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|模拟订单系统的组件的客户端的程序集文件。|  
|CableProvisioningSystemClient.csproj|C#项目文件。|  
|CPSClient.cs|客户端的源。 包括**OrderHandlerWrapper**类代码。|  
|OrderException.cs|C#类定义的文件**OrderException**。|  
  
 中的文件\<安装目录\>\CableProvisioningSystemServer  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|模拟订单系统的组件的服务器端的程序集文件。|  
|CableProvisioningSystemServer.csproj|C#项目文件。|  
|CableProvisioningSystemServer.csproj.user|Visual Studio 项目用户选项文件|  
|CPSServer.cs|源服务器。|  
  
 中的文件\<安装目录\>\CSRWebApp  
  
|文件|Description|  
|----------|-----------------|  
|CSRMainForm.aspx|客户服务输入的 ASP 窗体。|  
|CSRMainForm.aspx.cs|C#窗体后面的代码。|  
|Web.Config|在窗体的配置文件。|  
  
 中的文件\<安装目录\>\CSRWebApp\App_WebReferences\SouthridgeVideo_OrderBroker  
  
|文件|Description|  
|----------|-----------------|  
|orderbrokerorch_orderport.disco|Disco 文件**OrderBroker**显示为 web 服务。|  
|orderbrokerorch_orderport.discomap|生成的文件。|  
|orderbrokerorch_orderport.wsdl|WSDL 文件**OrderBroker**显示为 web 服务。|  
  
 中的文件\<安装目录\>\FacilitiesSimulator  
  
|文件|Description|  
|----------|-----------------|  
|FacilitiesSimulator.csproj|C#功能模拟程序的项目文件。|  
|FacilitiesSimulator.csproj.user|Visual Studio 项目用户选项文件|  
|FacilitiesSimulatorForm.cs|C#功能模拟程序的代码。|  
|FacilitiesSimulatorForm.resx|资源文件。|  
  
 中的文件\<安装目录\>\HistoryDB  
  
|文件|Description|  
|----------|-----------------|  
|CreateDatabase.cmd|来驱动创建历史记录数据库的 SQL 文件的文件。|  
|SouthridgeVideoHistory.sql|若要创建历史记录数据库的 SQL 命令。|  
  
 中的文件\<安装目录\>\IOperationsSystem  
  
|文件|Description|  
|----------|-----------------|  
|IOperationsSystem.cs|接口定义操作系统。|  
|IOperationsSystem.csproj|C#项目文件。|  
|IOperationsSystem.csproj.user|Visual Studio 项目用户选项文件|  
  
 中的文件\<安装目录\>\IOrderHandler  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|IOrderHandler.cs|接口定义**OrderHandler**。|  
|IOrderHandler.csproj|C#项目文件。|  
  
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
|OperationsClient.csproj|C#操作客户端项目。|  
|OpsClient.cs|C#操作客户端代码。|  
|OpsExceptions.cs|C#定义操作异常的代码。|  
  
 中的文件\<安装目录\>\OperationsHandler  
  
|文件|Description|  
|----------|-----------------|  
|OperationsHandler.csproj|C#操作处理程序的项目文件。|  
|OpsHandler.cs|C#为代码**OpsHandler**。 通过使用**OpsClient**发出请求的操作系统。|  
  
 中的文件\<安装目录\>\OperationsServer  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|OperationsServer.csproj|C#操作服务器的项目文件。|  
|OpsServer.cs|C#提供的实例的操作服务器代码**OpsHandler**对象。|  
  
 中的文件\<安装目录\>\OpsAdapter  
  
|文件|Description|  
|----------|-----------------|  
|OpsAdapter.sln|Ops 适配器的 visual Studio 解决方案。|  
|Register_Ops_Adapter.vbs|用于注册 Ops 适配器的 VBScript。|  
|SetupOpsAdapter.bat|用于安装 Ops 适配器的批处理文件。|  
  
 中的文件\<安装目录\>\OpsAdapter\IOpsAIC  
  
|文件|Description|  
|----------|-----------------|  
|IOpsAIC.cs|C#接口定义的代码文件**初始化**并**Execute** Ops 适配器调用的方法。|  
|IOpsAIC.csproj|C#项目文件。|  
  
 中的文件\<安装目录\>\OpsAdapter\OpsAdapterMgmt  
  
|文件|Description|  
|----------|-----------------|  
|AdapterManagement.cs|C#Ops 适配器的源文件。|  
|AssemblyInfo.cs|程序集信息文件。|  
|OpsAdapterMgmt.csproj|C#Ops 适配器的源文件。|  
|TransmitHandler.xsd|C#Ops 适配器的源文件。|  
|TransmitLocation.xsd|C#Ops 适配器的源文件。|  
  
 中的文件\<安装目录\>\OpsAdapter\OpsTxAdapter  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|OpsAdapterExceptions.cs|C#Ops 适配器的源文件。|  
|OpsAdapterProperties.cs|C#Ops 适配器的源文件。|  
|OpsTransmitAdapterBatch.cs|C#Ops 适配器的源文件。|  
|OpsTransmitter.cs|C#Ops 适配器的源文件。|  
|OpsTxAdapter.csproj|C#项目文件。|  
  
 中的文件\<安装目录\>\Orchestrations\CableOrderActions  
  
|文件|Description|  
|----------|-----------------|  
|Activate.odx|**激活**由订单处理阶段使用业务流程。|  
|Analyze.odx|**分析**由订单处理阶段使用业务流程。|  
|CableOrderActions.btproj|BizTalk 项目文件。|  
|Cancel.odx|**取消**由订单处理阶段使用业务流程。|  
|Change.odx|**更改**由订单处理阶段使用业务流程。|  
|Complete.odx|**完成**由订单处理阶段使用业务流程。|  
|Validate.odx|**验证**由订单处理阶段使用业务流程。|  
  
 中的文件\<安装目录\>\Orchestrations\CableOrderStage1  
  
|文件|Description|  
|----------|-----------------|  
|CableOrder1.odx|第一个订单处理阶段业务流程。|  
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
|CSR_OrderRequest_To_Order.btm|若要将客户服务订单请求转换为订单消息的映射。|  
|CSR_OrderRequest_To_Servicing_OrderRequest.btm|用于将客户服务订单请求转换到为服务消息映射|  
|CSR_OrderRequest_To_SQLHistoryInsert.btm|若要将客户服务订单请求转换为历史记录更新消息的映射。|  
|OrderBrokerMaps.btproj|BizTalk 项目文件。|  
|Order_To_CSR_OrderRequest.btm|用于将订单消息转换为客户服务订单请求的映射。|  
  
 中的文件\<安装目录\>\OrderBrokerSchemas  
  
|文件|Description|  
|----------|-----------------|  
|CSR_OrderRequest.xsd|客户服务请求的架构。|  
|OrderBrokerSchemas.btproj|BizTalk 项目文件。|  
|Servicing_OrderRequest.xsd|定义发送到服务系统的消息架构。|  
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
|OrderHandler.cs|C#为代码**OrderHandler**对象。|  
|OrderHandler.csproj|C#项目文件。|  
  
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
|InternalMessages.cs|C#定义用于在解决方案的组件之间进行通信的消息的类的代码。|  
|SchemaClasses.csproj|C#项目文件。|  
  
 中的文件\<安装目录\>\Schemas  
  
|文件|Description|  
|----------|-----------------|  
|Order.xsd|订单消息的架构。|  
|OrderPropertySchema.xsd|升级属性架构的订单消息。|  
|Schemas.btproj|BizTalk 项目文件。|  
  
 中的文件\<安装目录\>\Scripts  
  
|文件|Description|  
|----------|-----------------|  
|CleanDirs.cmd|若要删除文件仅执行的测试版本的解决方案结合使用的目录的命令文件。|  
|CreateAppReferences.vbs|VBScript 来创建应用程序的引用。|  
|CreateQueues.vbs|若要创建 MSMQ 队列的 VBScript。|  
|CreateSouthridgeVideoApplication.cmd|若要在 SSO 配置存储区中创建的配置值的命令文件。|  
|CreateTestDirectories.cmd|创建解决方案的测试版本的目录的命令文件。|  
|DeployBPM.cmd|若要将解决方案部署的命令文件。|  
|regac.bat|若要在全局程序集缓存 (GAC) 中注册程序集的批处理文件。|  
|SouthridgeVideoSSOConfiguration.xml|包含初始 SSO 配置值的文件。|  
  
 中的文件\<安装目录\>\ServiceLevelTracking  
  
|文件|Description|  
|----------|-----------------|  
|Activity_CustomerOrderRequest.cs|C#若要定义客户订单请求 BAM 活动的代码。|  
|Activity_OrderManager.cs|C#若要定义订单管理器 BAM 活动的代码。|  
|Activity_ServiceOrderRequest.cs|C#若要定义服务订单请求 BAM 活动的代码。|  
|ServiceLevelTracking.cs|C#代码以定义活动的抽象基类。|  
|ServiceLevelTracking.csproj|C#项目文件。|  
  
 中的文件\<安装目录\>\Utilities  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|CableOrderException.cs|C#定义电缆 order 异常类的代码。|  
|Helper.cs|C#各种助手类和方法的代码。|  
|Recaller.cs|C#为代码**Recaller**对象。|  
|SSOConfigHelper.cs|C#SSO 配置助手对象和方法的代码。|  
|Utilities.csproj|C#项目文件。|  
  
## <a name="see-also"></a>请参阅  
 [业务流程管理解决方案参考](../core/business-process-management-solution-reference.md)   
 [业务流程管理解决方案的组件](../core/components-of-the-business-process-management-solution.md)