---
title: "服务文件清单面向解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: service solution tutorial, file inventory
ms.assetid: 32c25372-31e1-4059-b4ed-f12e62f315d5
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39d18b32e1b499009e7559a68d7e60e6ba43f28c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="file-inventory-for-the-service-oriented-solution"></a>服务文件清单面向解决方案
本部分列出了面向服务的解决方案的子目录和源文件。 面向服务的解决方案源文件的默认安装目录为 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios\SO。 下表将具有此路径之前的说明\<安装 Directory\>。  
  
 中的文件\<安装目录\>\BTSSoln  
  
|文件|Description|  
|----------|-----------------|  
|Microsoft.Samples.BizTalk.WoodgroveBank.sln|Visual Studio 解决方案文件。|  
|ReplacePKToken.vbs|构建解决方案时用于修复解决方案文件中公钥标记的 VBScript。|  
|ReplacePKToken.wsf|ReplacePKToken VBScript 的 Windows 脚本文件。|  
|SetupBTSSoln.bat|创建公钥，更新指向公钥的引用和编译解决方案。 有关部署解决方案的信息，请参阅[部署服务面向解决方案](../core/deploying-the-service-oriented-solution.md)。|  
  
 中的文件\<安装目录\>\BTSSoln\BAM  
  
|文件|Description|  
|----------|-----------------|  
|ServiceLevelTracking.xls|BAM 数据的 Excel 电子表格。|  
|ServiceLevelTracking.xml|定义 BAM 数据项类型的架构。|  
  
 中的文件\<安装目录\>\BTSSoln\Bindings  
  
|文件|Description|  
|----------|-----------------|  
|AdapterSOAOrchBindings.xml|解决方案的适配器版本的绑定文件。|  
|InlineSOAOrchBindings.xml|解决方案的内联版本的绑定文件。|  
|StubSOAOrchBindings.xml|解决方案的存根版本的绑定文件。|  
  
 中的文件\<安装目录\>\BTSSoln\ConfigHelper  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|ConfigHelper.csproj|C# 项目文件。|  
|ConfigParameters.cs|用于 SSO 配置助手方法的 C# 代码文件。|  
|ConfigPropertyBag.cs|用于 SSO 配置助手方法使用的属性包的 C# 代码文件。|  
  
 中的文件\<安装目录\>\BTSSoln\ErrorHelper  
  
|文件|Description|  
|----------|-----------------|  
|CustomerServiceErrors.cs|用于客户服务错误的 C# 代码文件。|  
|ErrorHelper.csproj|C# 项目文件。|  
  
 中的文件\<安装目录\>\BTSSoln\InPipeline  
  
|文件|Description|  
|----------|-----------------|  
|InPipeline.btp|将 SSO 票证添加到消息中的接收管道。|  
|InPipeline.btproj|BizTalk 项目文件。|  
  
 中的文件\<安装目录\>\BTSSoln\InPipelineComp  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|InPipelineComp.csproj|C# 项目文件。|  
|SSOTicketIssuer.cs|用于颁发 SSO 票证的管道组件的 C# 代码文件。|  
|SSOTicketIssuer.resx|资源文件。|  
|SSOTicketIssuerIcon.bmp|管道组件图标文件。|  
  
 中的文件\<安装目录\>\BTSSoln\Maps  
  
|文件|Description|  
|----------|-----------------|  
|Aggregate_To_CustomerServiceResponse.btm|将来自后端系统的三个响应的聚合转换为单个响应消息的映射。|  
|Aggregate_To_ErrorResponse.btm|在出错时将三个响应的聚合转换为单个错误响应的映射。|  
|CustomerServiceRequest_To_CreditLimiRequest.btm|将客户服务请求转换为消息以请求信用限额的映射。|  
|CustomerServiceRequest_To_CreditLimitResponse.btm|将客户服务请求转换为消息以使用信用限额进行响应的映射。|  
|CustomerServiceRequest_To_CustomerServiceResponseDenied.btm|将客户服务请求转换为“请求被拒绝”消息的映射。|  
|CustomerServiceRequest_To_LastPaymentRequest.btm|将客户服务请求转换为请求最近付款信息的消息的映射。|  
|CustomerServiceRequest_To_LastPaymentResponseTimeout.btm|将客户服务请求转换为最近付款响应消息的映射。|  
|CustomerServiceRequest_To_PendingTransactionResponse.btm|将客户服务请求转换为挂起事务响应消息的映射。|  
|CustomerServiceRequest_To_PendingTransactionsRequest.btm|将客户服务请求转换为请求挂起事务信息的消息的映射。|  
|Maps.btproj|BizTalk 项目文件。|  
  
 中的文件\<安装目录\>\BTSSoln\Orchestrations\Adapter  
  
|文件|Description|  
|----------|-----------------|  
|CustomerService.odx|适配器版本**CustomerService**业务流程。|  
|CustomerServiceNativeRequestResponse.odx|为提供服务为前端的业务流程的适配器版本**CustomerService**业务流程。|  
|CustomerServiceReceiveSend.odx|为提供服务为前端的业务流程的适配器版本**CustomerService**业务流程。|  
|Orchestrations.Adapter.btproj|BizTalk 项目文件。|  
  
 中的文件\<安装目录\>\BTSSoln\Orchestrations\Adapter\Web References\PendTransWS  
  
|文件|Description|  
|----------|-----------------|  
|PendTransWS.disco|生成的文件。|  
|PendTransWS.wsdl|生成的文件。|  
|Reference.map|生成的文件。|  
|Reference.map.cs|生成的文件|  
|Reference.odx|生成的文件。|  
|Reference.xsd|生成的文件。|  
|Reference1.xsd|生成的文件。|  
  
 中的文件\<安装目录\>\BTSSoln\Orchestrations\Adapter\Web References\StubSAPWS  
  
|文件|Description|  
|----------|-----------------|  
|Reference.map|生成的文件。|  
|Reference.map.cs|生成的文件。|  
|Reference.odx|生成的文件。|  
|Reference.xsd|生成的文件。|  
|StubSAPWS.disco|生成的文件。|  
|StubSAPWS.wsdl|生成的文件。|  
  
 中的文件\<安装目录\>\BTSSoln\Orchestrations\Inline  
  
|文件|Description|  
|----------|-----------------|  
|CustomerService.odx|内联版本**CustomerService**业务流程。|  
|CustomerServiceNativeRequestResponse.odx|为提供服务为前端的业务流程的内联版本**CustomerService**业务流程。|  
|CustomerServiceReceiveSend.odx|为提供服务为前端的业务流程的内联版本**CustomerService**业务流程。|  
|Orchestrations.Inline.btproj|BizTalk 项目文件。|  
  
 中的文件\<安装目录\>\BTSSoln\Orchestrations\Stub  
  
|文件|Description|  
|----------|-----------------|  
|CustomerService.odx|存根 （stub） 版本**CustomerService**业务流程。|  
|CustomerServiceNativeRequestResponse.odx|为提供服务为前端的业务流程的存根 （stub） 版本**CustomerService**业务流程。|  
|Orchestrations.Stub.btproj|BizTalk 项目文件。|  
  
 中的文件\<安装目录\>\BTSSoln\Orchestrations\Stub\Web References\StubPendTransWS  
  
|文件|Description|  
|----------|-----------------|  
|Reference.map|生成的文件。|  
|Reference.map.cs|生成的文件。|  
|Reference.odx|生成的文件。|  
|Reference.xsd|生成的文件。|  
|Reference1.xsd|生成的文件。|  
|StubPendTransWS.disco|生成的文件。|  
|StubPendTransWS.wsdl|生成的文件。|  
  
 中的文件\<安装目录\>\BTSSoln\Orchestrations\Stub\Web References\StubPmntTrckWS  
  
|文件|Description|  
|----------|-----------------|  
|Reference.map|生成的文件。|  
|Reference.map.cs|生成的文件。|  
|Reference.odx|生成的文件。|  
|Reference.xsd|生成的文件。|  
|Reference1.xsd|生成的文件。|  
|StubPmntTrckWS.disco|生成的文件。|  
|StubPmntTrckWS.wsdl|生成的文件。|  
  
 中的文件\<安装目录\>\BTSSoln\Orchestrations\Stub\Web References\StubSAPWS  
  
|文件|Description|  
|----------|-----------------|  
|Reference.map|生成的文件。|  
|Reference.map.cs|生成的文件。|  
|Reference.odx|生成的文件。|  
|Reference.xsd|生成的文件。|  
|StubSAPWS.disco|生成的文件。|  
|StubSAPWS.wsdl|生成的文件。|  
  
 中的文件\<安装目录\>\BTSSoln\OrchProxy\Adapter  
  
|文件|Description|  
|----------|-----------------|  
|CustomerServicePort.asmx|生成的文件。|  
|Global.asax|生成的文件。|  
|Global.asax.resx|生成的文件。|  
|OrchProxy.Adapter.csproj.webinfo|生成的文件。|  
|TraceExtension.cs|生成的文件。|  
|Web.config|生成的文件。|  
|WsdlExtension.cs|生成的文件。|  
  
 中的文件\<安装目录\>\BTSSoln\OrchProxy\Adapter\app_code  
  
|文件|Description|  
|----------|-----------------|  
|assemblyinfo.cs|生成的文件。|  
|customerserviceport.asmx.cs|生成的文件。|  
|datatypes.cs|生成的文件。|  
|global.asax.cs|生成的文件。|  
  
 中的文件\<安装目录\>\BTSSoln\OrchProxy\Inline  
  
|文件|Description|  
|----------|-----------------|  
|CustomerServicePort.asmx|生成的文件。|  
|Global.asax|生成的文件。|  
|Global.asax.resx|生成的文件。|  
|OrchProxy.Inline.csproj.webinfo|生成的文件。|  
|TraceExtension.cs|生成的文件。|  
|Web.config|生成的文件。|  
|WsdlExtension.cs|生成的文件。|  
  
 中的文件\<安装目录\>\BTSSoln\OrchProxy\Inline\app_code  
  
|文件|Description|  
|----------|-----------------|  
|assemblyinfo.cs|生成的文件。|  
|customerserviceport.asmx.cs|生成的文件。|  
|datatypes.cs|生成的文件。|  
|global.asax.cs|生成的文件。|  
  
 中的文件\<安装目录\>\BTSSoln\OrchProxy\Stub  
  
|文件|Description|  
|----------|-----------------|  
|CustomerServicePort.asmx|生成的文件。|  
|Global.asax|生成的文件。|  
|Global.asax.resx|生成的文件。|  
|OrchProxy.Stub.csproj.webinfo|生成的文件。|  
|TraceExtension.cs|生成的文件。|  
|Web.config|生成的文件。|  
|WsdlExtension.cs|生成的文件。|  
  
 中的文件\<安装目录\>\BTSSoln\OrchProxy\Stub\app_code  
  
|文件|Description|  
|----------|-----------------|  
|assemblyinfo.cs|生成的文件。|  
|customerserviceport.asmx.cs|生成的文件。|  
|datatypes.cs|生成的文件。|  
|global.asax.cs|生成的文件。|  
  
 中的文件\<安装目录\>\BTSSoln\PaymentTracker  
  
|文件|Description|  
|----------|-----------------|  
|App.ico|付款跟踪模拟程序的图标文件。|  
|AssemblyInfo.cs|程序集信息文件。|  
|MessageProcessor.cs|用于处理付款跟踪程序消息并返回相应响应的类 C# 代码。|  
|PaymentTracker.cs|用于模拟付款跟踪程序系统的类的 C# 代码。|  
|PaymentTracker.csproj|C# 项目文件。|  
|PaymentTrackerSimulator.cs|用于付款跟踪模拟程序的服务器的 C# 代码。|  
|runit.cmd|用于启动付款跟踪模拟程序的命令文件。|  
  
 中的文件\<安装目录\>\BTSSoln\PaymentTrackerCall  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|Exceptions.cs|用于定义付款跟踪系统异常的 C# 代码。|  
|PaymentTrackerCall.csproj|C# 项目文件。|  
|PaymentTrackerCaller.cs|用于从业务流程调用付款跟踪系统内联的 C# 代码。|  
  
 中的文件\<安装目录\>\BTSSoln\PendTransCall  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|Exceptions.cs|用于定义挂起事务系统异常的 C# 代码。|  
|PendingTransactionsCaller.cs|用于从业务流程调用挂起事务系统内联的 C# 代码。|  
|PendingTransactionsWebService.disco|生成的文件。|  
|PendingTransactionsWebService.wsdl|生成的文件。|  
|PendTransCall.csproj|C# 项目文件。|  
|WebServiceReference.cs|生成的文件。|  
  
 中的文件\<安装目录\>\BTSSoln\PmTrkPipeline  
  
|文件|Description|  
|----------|-----------------|  
|PaymentTrackerReceivePipeline.btp|付款跟踪系统的接收管道。|  
|PaymentTrackerSendPipeline.btp|付款跟踪系统的发送管道。|  
|PmTrkPipeline.btproj|BizTalk 项目文件。|  
  
 中的文件\<安装目录\>\BTSSoln\PmTrkPipelineComp  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|MQSeriesHeaderSetter.cs|管道组件的 C# 代码，用于处理进入或来自付款跟踪系统的消息的某些 MQSeries 消息标头设置。|  
|MQSeriesHeaderSetter.resx|资源文件。|  
|PmTrkPipelineComp.csproj|C# 项目文件。|  
  
 中的文件\<安装目录\>\BTSSoln\SchemaClasses  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|BAPI_BANKACCT_GET_DETAIL.cs|从相应的架构 (.xsd) 文件生成。|  
|CustomerServiceRequest.cs|从相应的架构 (.xsd) 文件生成。|  
|CustomerServiceResponse.cs|从相应的架构 (.xsd) 文件生成。|  
|LastPaymentRequest.cs|从相应的架构 (.xsd) 文件生成。|  
|LastPaymentResponse.cs|从相应的架构 (.xsd) 文件生成。|  
|PendingTransactionsRequest.cs|从相应的架构 (.xsd) 文件生成。|  
|PendingTransactionsResponse.cs|从相应的架构 (.xsd) 文件生成。|  
|SchemaClasses.csproj|C# 项目文件。|  
  
 中的文件\<安装目录\>\BTSSoln\Schemas  
  
|文件|Description|  
|----------|-----------------|  
|BAPI_BANKACCT_GET_DETAIL.xsd|SAP 请求和响应消息的架构。|  
|CustomerServiceRequest.xsd|客户服务请求消息的架构。|  
|CustomerServiceResponse.xsd|客户服务响应消息的架构。|  
|genClasses.cmd|用于从架构生成 C# 类文件的命令文件。|  
|LastPaymentRequest.xsd|最近付款请求消息的架构。|  
|LastPaymentResponse.xsd|最近付款响应消息的架构。|  
|PendingTransactionsRequest.xsd|挂起事务请求消息的架构。|  
|PendingTransactionsResponse.xsd|挂起事务响应消息的架构。|  
|Schemas.btproj|BizTalk 项目文件。|  
  
 中的文件\<安装目录\>\BTSSoln\Scripts  
  
|文件|Description|  
|----------|-----------------|  
|ConfigStoreApp.xml|定义 SSO 配置值的 XML 文件。|  
|CreateInitialConfigInSSO.cmd|创建初始 SSO 配置值的命令文件。|  
|DeployAllBinding.cmd|部署所有程序集的命令文件。|  
|DeployStubBinding.cmd|部署存根版本的程序集的命令文件。|  
|PendTransAffApp.xml|定义挂起事务关联应用程序的值的 XML 文件。|  
|PendTransUserMap.xml|为挂起事务关联应用程序的用户定义凭据映射的 XML 文件。|  
|PmntTrckAffApp.xml|定义挂起事务关联应用程序的值的 XML 文件。|  
|PmntTrckUserMap.xml|为付款跟踪关联应用程序的用户定义凭据映射的 XML 文件。|  
|RemoveReceivePort.vbs|用于删除接收端口的通用 VBScript。|  
|RemoveSendPort.vbs|用于删除发送端口的通用 VBScript。|  
|SetConfigValuesInSSO.cmd|用于设置 SSO 中的配置值的命令文件。|  
|StartAll.vbs|用于登记和启动所有业务流程的命令文件。|  
|StartStub.vbs|用于登记和启动存根版本的业务流程的命令文件。|  
|UndeployAll.cmd|用于取消部署所有程序集的命令文件。|  
|UndeployStub.cmd|用于取消部署存根版本的程序集的命令文件。|  
|UnEnlistAll.vbs|用于取消登记所有业务流程的命令文件。|  
|UnEnlistStub.vbs|用于取消登记存根版本的业务流程的命令文件。|  
  
 中的文件\<安装目录\>\BTSSoln\ServiceLevelTracking  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|ServiceLevelTracking.cs|用于服务级别 BAM 跟踪的 C# 助手函数。|  
|ServiceLevelTracking.csproj|C# 项目文件。|  
  
 中的文件\<安装目录\>\BTSSoln\SimpleClient  
  
|文件|Description|  
|----------|-----------------|  
|AdapterCustomerServicePort.disco|生成的文件。|  
|AdapterCustomerServicePort.wsdl|生成的文件。|  
|App.ico|简单客户端应用程序的图标文件。|  
|AssemblyInfo.cs|程序集信息文件。|  
|InlineCustomerServicePort.disco|生成的文件。|  
|InlineCustomerServicePort.wsdl|生成的文件。|  
|SimpleClient.cs|用于发出请求的简单 Windows 窗体应用程序。|  
|SimpleClient.csproj|C# 项目文件。|  
|SimpleClient.resx|资源文件。|  
|WebServiceReferences.cs|生成的文件。|  
  
 中的文件\<安装目录\>\BTSSoln\StubWebServices\PaymentTrack  
  
|文件|Description|  
|----------|-----------------|  
|Global.asax|生成的文件。|  
|Global.asax.resx|生成的文件。|  
|StubPmntTrck.csproj.webinfo|生成的文件。|  
|StubPmntTrckWS.asmx|生成的文件。|  
|StubPmntTrckWS.asmx.resx|生成的文件。|  
|Web.config|生成的文件。|  
  
 中的文件\<安装目录\>\BTSSoln\StubWebServices\PaymentTrack\app_code  
  
|文件|Description|  
|----------|-----------------|  
|assemblyinfo.cs|程序集信息文件。|  
|global.asax.cs|生成的文件。|  
|StubPmntTrckWS.asmx.cs|生成的文件。|  
  
 中的文件\<安装目录\>\BTSSoln\StubWebServices\PendingTrans  
  
|文件|Description|  
|----------|-----------------|  
|Global.asax|生成的文件。|  
|Global.asax.resx|生成的文件。|  
|StubPendTransWS.asmx|生成的文件。|  
|StubPendTransWS.asmx.resx|生成的文件。|  
|StubPendTransWS.csproj.webinfo|生成的文件。|  
|Web.config|生成的文件。|  
  
 中的文件\<安装目录\>\BTSSoln\StubWebServices\PendingTrans\app_code  
  
|文件|Description|  
|----------|-----------------|  
|assemblyinfo.cs|生成的文件。|  
|global.asax.cs|生成的文件。|  
|StubPendTransWS.asmx.cs|生成的文件。|  
  
 中的文件\<安装目录\>\BTSSoln\StubWebServices\SAP  
  
|文件|Description|  
|----------|-----------------|  
|Global.asax|生成的文件。|  
|Global.asax.resx|生成的文件。|  
|StubSAP.csproj.webinfo|生成的文件。|  
|StubSAPWS.asmx|生成的文件。|  
|StubSAPWS.asmx.resx|生成的文件。|  
|Web.config|生成的文件。|  
  
 中的文件\<安装目录\>\BTSSoln\StubWebServices\SAP\app_code  
  
|文件|Description|  
|----------|-----------------|  
|assemblyinfo.cs|程序集信息文件。|  
|global.asax.cs|生成的文件。|  
|stubsapws.asmx.cs|生成的文件。|  
  
 中的文件\<安装目录\>\BTSSoln\StubWebServices\StubSAPCall  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|Exceptions.cs|用于定义存根 SAP 调用超时异常的 C# 代码。|  
|StubSAPCall.csproj|C# 项目文件。|  
|StubSAPCallHelper.cs|用于调用存根 SAP Web Services 的助手程序集的 C# 代码。|  
|StubSAPWSProxy.cs|用于调用存根 SAP Web Services 的助手程序集的 C# 代码。|  
  
 中的文件\<安装目录\>\BTSSoln\Utilities  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|CustomerServiceHelper.cs|用于助手方法和类的 C# 代码。|  
|ReceivePipelineHelper.cs|用于通过业务流程调用管道的助手程序集的 C# 代码。|  
|Utilities.csproj|C# 项目文件。|  
  
 中的文件\<安装目录\>\MFAccess  
  
|文件|Description|  
|----------|-----------------|  
|Microsoft.Samples.BizTalk.WoodgroveBank.MainframeAccess.sln|Visual Studio 解决方案文件。|  
|SetupMFAccess.bat|用于生成解决方案的大型机访问组件的批处理文件。|  
  
 中的文件\<安装目录\>\MFAccess\HISTIComponent  
  
|文件|Description|  
|----------|-----------------|  
|bizcbl.txt|在大型机上运行的 COBOL 程序。|  
|HISTIComponent.tiproj|事务集成器项目文件。|  
|MainFrameProgramVTCS2Description.txt|事务集成器导出文件。|  
|SOHISTIUsingCOM.TLB|类型库。|  
  
 中的文件\<安装目录\>\MFAccess\HISTISimpleTester  
  
|文件|Description|  
|----------|-----------------|  
|App.ico|图标文件|  
|AssemblyInfo.cs|程序集信息文件。|  
|Form1.cs|用于测试与大型机的连接的 Windows 窗体程序。|  
|Form1.resx|资源文件|  
|HISTISimpleTester.csproj|C# 项目文件。|  
|Interop.SOHISTIUsingCOM.dll.reg|DLL 注册文件。|  
  
 中的文件\<安装目录\>\MFAccess\PendingTransactions  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|Global.asax|生成的文件。|  
|Global.asax.cs|生成的文件。|  
|Global.asax.resx|生成的文件。|  
|PendingTransactions.csproj|C# 项目文件。|  
|PendingTransactions.csproj.webinfo|生成的文件。|  
|PendTransWS.asmx|生成的文件。|  
|PendTransWS.asmx.cs|生成的文件。|  
|PendTransWS.asmx.resx|生成的文件。|  
|Web.config|生成的文件。|  
  
 中的文件\<安装目录\>\MFAccess\SchemaClasses  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|BAPI_BANKACCT_GET_DETAIL.cs|从相应的架构 (.xsd) 文件生成的 C# 类。|  
|CustomerServiceRequest.cs|从相应的架构 (.xsd) 文件生成的 C# 类。|  
|CustomerServiceResponse.cs|从相应的架构 (.xsd) 文件生成的 C# 类。|  
|LastPaymentRequest.cs|从相应的架构 (.xsd) 文件生成的 C# 类。|  
|LastPaymentResponse.cs|从相应的架构 (.xsd) 文件生成的 C# 类。|  
|PendingTransactionsRequest.cs|从相应的架构 (.xsd) 文件生成的 C# 类。|  
|PendingTransactionsResponse.cs|从相应的架构 (.xsd) 文件生成的 C# 类。|  
|SchemaClasses.csproj|C# 项目文件。|  
  
## <a name="see-also"></a>另请参阅  
 [服务组件面向解决方案](../core/components-of-the-service-oriented-solution.md)   
 [面向服务的解决方案参考](../core/service-oriented-solution-reference.md)