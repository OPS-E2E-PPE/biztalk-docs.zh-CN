---
title: 面向服务的文件清单的解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, file inventory
ms.assetid: 32c25372-31e1-4059-b4ed-f12e62f315d5
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 172d3d1495b14655f66a9ce11e616a3cb456dcab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345493"
---
# <a name="file-inventory-for-the-service-oriented-solution"></a>面向服务的文件清单的解决方案
本部分列出了子目录和源文件的面向服务的解决方案。 面向服务的解决方案源文件的默认安装目录[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios\SO。 下表来代替此路径与之前的说明\<安装目录\>。  
  
 中的文件\<安装目录\>\BTSSoln  
  
|文件|Description|  
|----------|-----------------|  
|Microsoft.Samples.BizTalk.WoodgroveBank.sln|Visual Studio 解决方案文件。|  
|ReplacePKToken.vbs|若要修复解决方案文件中的公钥标记，构建解决方案时的 VBScript。|  
|ReplacePKToken.wsf|ReplacePKToken VBScript 的 Windows 脚本文件。|  
|SetupBTSSoln.bat|创建一个公共密钥、 更新引用的公钥，并编译解决方案。 部署解决方案的信息，请参阅[部署面向服务的解决方案](../core/deploying-the-service-oriented-solution.md)。|  
  
 中的文件\<安装目录\>\BTSSoln\BAM  
  
|文件|Description|  
|----------|-----------------|  
|ServiceLevelTracking.xls|BAM 数据的 Excel 电子表格。|  
|ServiceLevelTracking.xml|定义 BAM 数据项类型的架构。|  
  
 中的文件\<安装目录\>\BTSSoln\Bindings  
  
|文件|Description|  
|----------|-----------------|  
|AdapterSOAOrchBindings.xml|该解决方案的适配器版本的绑定文件。|  
|InlineSOAOrchBindings.xml|该解决方案的内联版本的绑定文件。|  
|StubSOAOrchBindings.xml|该解决方案的存根版本的绑定文件。|  
  
 中的文件\<安装目录\>\BTSSoln\ConfigHelper  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|ConfigHelper.csproj|C#项目文件。|  
|ConfigParameters.cs|C#SSO 配置助手方法的代码文件。|  
|ConfigPropertyBag.cs|C#属性包使用的 SSO 配置助手方法的代码文件。|  
  
 中的文件\<安装目录\>\BTSSoln\ErrorHelper  
  
|文件|Description|  
|----------|-----------------|  
|CustomerServiceErrors.cs|C#客户服务错误的代码文件。|  
|ErrorHelper.csproj|C#项目文件。|  
  
 中的文件\<安装目录\>\BTSSoln\InPipeline  
  
|文件|Description|  
|----------|-----------------|  
|InPipeline.btp|接收管道将 SSO 票证添加到消息。|  
|InPipeline.btproj|BizTalk 项目文件。|  
  
 中的文件\<安装目录\>\BTSSoln\InPipelineComp  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|InPipelineComp.csproj|C#项目文件。|  
|SSOTicketIssuer.cs|C#用于颁发 SSO 票证的管道组件代码文件。|  
|SSOTicketIssuer.resx|资源文件。|  
|SSOTicketIssuerIcon.bmp|管道组件的图标文件。|  
  
 中的文件\<安装目录\>\BTSSoln\Maps  
  
|文件|Description|  
|----------|-----------------|  
|Aggregate_To_CustomerServiceResponse.btm|从后端系统的三个响应的聚合转换为单个响应消息映射。|  
|Aggregate_To_ErrorResponse.btm|若要将三个响应的聚合转换成单个错误响应，发生错误时的映射。|  
|CustomerServiceRequest_To_CreditLimiRequest.btm|若要将客户服务请求转换为消息以请求信用限额的映射。|  
|CustomerServiceRequest_To_CreditLimitResponse.btm|若要将客户服务请求转换为使用信用限额进行响应的消息的映射。|  
|CustomerServiceRequest_To_CustomerServiceResponseDenied.btm|用于将客户服务请求转换为请求被拒绝消息的映射。|  
|CustomerServiceRequest_To_LastPaymentRequest.btm|将客户服务请求转换为请求最近付款信息的消息的映射。|  
|CustomerServiceRequest_To_LastPaymentResponseTimeout.btm|若要将客户服务请求转换为最近付款响应消息的映射。|  
|CustomerServiceRequest_To_PendingTransactionResponse.btm|若要将客户服务请求转换为挂起事务响应消息的映射。|  
|CustomerServiceRequest_To_PendingTransactionsRequest.btm|将客户服务请求转换为请求挂起事务信息的消息的映射。|  
|Maps.btproj|BizTalk 项目文件。|  
  
 中的文件\<安装目录\>\BTSSoln\Orchestrations\Adapter  
  
|文件|Description|  
|----------|-----------------|  
|CustomerService.odx|适配器版本的**CustomerService**业务流程。|  
|CustomerServiceNativeRequestResponse.odx|适配器版本的业务流程用作前端**CustomerService**业务流程。|  
|CustomerServiceReceiveSend.odx|适配器版本的业务流程用作前端**CustomerService**业务流程。|  
|Orchestrations.Adapter.btproj|BizTalk 项目文件。|  
  
 中的文件\<安装目录\>references\pendtransws  
  
|文件|Description|  
|----------|-----------------|  
|PendTransWS.disco|生成的文件。|  
|PendTransWS.wsdl|生成的文件。|  
|Reference.map|生成的文件。|  
|Reference.map.cs|生成的文件|  
|Reference.odx|生成的文件。|  
|Reference.xsd|生成的文件。|  
|Reference1.xsd|生成的文件。|  
  
 中的文件\<安装目录\>references\stubsapws  
  
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
|CustomerServiceNativeRequestResponse.odx|内联版本的业务流程用作前端**CustomerService**业务流程。|  
|CustomerServiceReceiveSend.odx|内联版本的业务流程用作前端**CustomerService**业务流程。|  
|Orchestrations.Inline.btproj|BizTalk 项目文件。|  
  
 中的文件\<安装目录\>\BTSSoln\Orchestrations\Stub  
  
|文件|Description|  
|----------|-----------------|  
|CustomerService.odx|存根版本**CustomerService**业务流程。|  
|CustomerServiceNativeRequestResponse.odx|存根版本的业务流程用作前端**CustomerService**业务流程。|  
|Orchestrations.Stub.btproj|BizTalk 项目文件。|  
  
 中的文件\<安装目录\>references\stubpendtransws  
  
|文件|Description|  
|----------|-----------------|  
|Reference.map|生成的文件。|  
|Reference.map.cs|生成的文件。|  
|Reference.odx|生成的文件。|  
|Reference.xsd|生成的文件。|  
|Reference1.xsd|生成的文件。|  
|StubPendTransWS.disco|生成的文件。|  
|StubPendTransWS.wsdl|生成的文件。|  
  
 中的文件\<安装目录\>references\stubpmnttrckws  
  
|文件|Description|  
|----------|-----------------|  
|Reference.map|生成的文件。|  
|Reference.map.cs|生成的文件。|  
|Reference.odx|生成的文件。|  
|Reference.xsd|生成的文件。|  
|Reference1.xsd|生成的文件。|  
|StubPmntTrckWS.disco|生成的文件。|  
|StubPmntTrckWS.wsdl|生成的文件。|  
  
 中的文件\<安装目录\>references\stubsapws  
  
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
|MessageProcessor.cs|C#一个类来处理付款跟踪程序消息并返回相应响应的代码。|  
|PaymentTracker.cs|C#模拟付款跟踪程序系统的类的代码。|  
|PaymentTracker.csproj|C#项目文件。|  
|PaymentTrackerSimulator.cs|C#付款跟踪模拟程序的服务器代码。|  
|runit.cmd|用于启动付款跟踪模拟程序的命令文件。|  
  
 中的文件\<安装目录\>\BTSSoln\PaymentTrackerCall  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|Exceptions.cs|C#用于定义付款跟踪系统异常的代码。|  
|PaymentTrackerCall.csproj|C#项目文件。|  
|PaymentTrackerCaller.cs|C#若要调用付款跟踪系统内联用于从业务流程的代码。|  
  
 中的文件\<安装目录\>\BTSSoln\PendTransCall  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|Exceptions.cs|C#用于定义挂起事务系统异常的代码。|  
|PendingTransactionsCaller.cs|C#若要从业务流程调用挂起事务系统内联的代码。|  
|PendingTransactionsWebService.disco|生成的文件。|  
|PendingTransactionsWebService.wsdl|生成的文件。|  
|PendTransCall.csproj|C#项目文件。|  
|WebServiceReference.cs|生成的文件。|  
  
 中的文件\<安装目录\>\BTSSoln\PmTrkPipeline  
  
|文件|Description|  
|----------|-----------------|  
|PaymentTrackerReceivePipeline.btp|接收管道为付款跟踪系统。|  
|PaymentTrackerSendPipeline.btp|发送管道的付款跟踪系统。|  
|PmTrkPipeline.btproj|BizTalk 项目文件。|  
  
 中的文件\<安装目录\>\BTSSoln\PmTrkPipelineComp  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|MQSeriesHeaderSetter.cs|C#管道组件来处理消息进入或来自付款跟踪系统的某些 MQSeries 消息标头设置的代码...|  
|MQSeriesHeaderSetter.resx|资源文件。|  
|PmTrkPipelineComp.csproj|C#项目文件。|  
  
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
|SchemaClasses.csproj|C#项目文件。|  
  
 中的文件\<安装目录\>\BTSSoln\Schemas  
  
|文件|Description|  
|----------|-----------------|  
|BAPI_BANKACCT_GET_DETAIL.xsd|SAP 请求和响应消息的架构。|  
|CustomerServiceRequest.xsd|客户服务请求消息的架构。|  
|CustomerServiceResponse.xsd|客户服务响应消息的架构。|  
|genClasses.cmd|要生成的命令文件C#类的架构中的文件。|  
|LastPaymentRequest.xsd|最近付款请求消息的架构。|  
|LastPaymentResponse.xsd|最近付款响应消息的架构。|  
|PendingTransactionsRequest.xsd|挂起事务请求消息的架构。|  
|PendingTransactionsResponse.xsd|挂起事务响应消息的架构。|  
|Schemas.btproj|BizTalk 项目文件。|  
  
 中的文件\<安装目录\>\BTSSoln\Scripts  
  
|文件|Description|  
|----------|-----------------|  
|ConfigStoreApp.xml|定义 SSO 配置值的 XML 文件。|  
|CreateInitialConfigInSSO.cmd|若要创建初始 SSO 配置值的命令文件。|  
|DeployAllBinding.cmd|若要部署所有程序集的命令文件。|  
|DeployStubBinding.cmd|若要部署的程序集的存根版本的命令文件。|  
|PendTransAffApp.xml|XML 文件定义的值为挂起事务关联应用程序。|  
|PendTransUserMap.xml|定义挂起事务关联应用程序的用户的凭据映射的 XML 文件。|  
|PmntTrckAffApp.xml|XML 文件定义的值为挂起事务关联应用程序。|  
|PmntTrckUserMap.xml|定义凭据映射的付款跟踪关联应用程序的用户的 XML 文件。|  
|RemoveReceivePort.vbs|若要删除接收端口的通用 VBScript。|  
|RemoveSendPort.vbs|若要删除的发送端口的通用 VBScript。|  
|SetConfigValuesInSSO.cmd|若要在 SSO 中设置的配置值的命令文件。|  
|StartAll.vbs|以登记并启动所有业务流程的命令文件。|  
|StartStub.vbs|以登记并启动业务流程的存根版本的命令文件。|  
|UndeployAll.cmd|若要取消部署所有程序集的命令文件。|  
|UndeployStub.cmd|若要取消部署存根版本的程序集的命令文件。|  
|UnEnlistAll.vbs|若要取消登记所有业务流程的命令文件。|  
|UnEnlistStub.vbs|若要取消登记存根版本的业务流程的命令文件。|  
  
 中的文件\<安装目录\>\BTSSoln\ServiceLevelTracking  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|ServiceLevelTracking.cs|C#服务级别 BAM 跟踪的帮助程序函数。|  
|ServiceLevelTracking.csproj|C#项目文件。|  
  
 中的文件\<安装目录\>\BTSSoln\SimpleClient  
  
|文件|Description|  
|----------|-----------------|  
|AdapterCustomerServicePort.disco|生成的文件。|  
|AdapterCustomerServicePort.wsdl|生成的文件。|  
|App.ico|简单的客户端应用程序的图标文件。|  
|AssemblyInfo.cs|程序集信息文件。|  
|InlineCustomerServicePort.disco|生成的文件。|  
|InlineCustomerServicePort.wsdl|生成的文件。|  
|SimpleClient.cs|用于发出请求的简单 Windows 窗体应用程序。|  
|SimpleClient.csproj|C#项目文件。|  
|SimpleClient.resx|资源文件。|  
|WebServiceReferences.cs|生成的文件。|  
  
 Files in \<Install Directory\>\BTSSoln\StubWebServices\PaymentTrack  
  
|文件|Description|  
|----------|-----------------|  
|Global.asax|生成的文件。|  
|Global.asax.resx|生成的文件。|  
|StubPmntTrck.csproj.webinfo|生成的文件。|  
|StubPmntTrckWS.asmx|生成的文件。|  
|StubPmntTrckWS.asmx.resx|生成的文件。|  
|Web.config|生成的文件。|  
  
 Files in \<Install Directory\>\BTSSoln\StubWebServices\PaymentTrack\app_code  
  
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
  
 Files in \<Install Directory\>\BTSSoln\StubWebServices\PendingTrans\app_code  
  
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
|Exceptions.cs|C#用于定义存根 SAP 调用超时异常的代码。|  
|StubSAPCall.csproj|C#项目文件。|  
|StubSAPCallHelper.cs|C#用于调用存根 SAP web 服务的帮助程序程序集代码。|  
|StubSAPWSProxy.cs|C#用于调用存根 SAP web 服务的帮助程序程序集代码。|  
  
 中的文件\<安装目录\>\BTSSoln\Utilities  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|CustomerServiceHelper.cs|C#帮助器方法和类的代码。|  
|ReceivePipelineHelper.cs|C#调用管道的助手的帮助程序程序集代码。|  
|Utilities.csproj|C#项目文件。|  
  
 中的文件\<安装目录\>\MFAccess  
  
|文件|Description|  
|----------|-----------------|  
|Microsoft.Samples.BizTalk.WoodgroveBank.MainframeAccess.sln|Visual Studio 解决方案文件。|  
|SetupMFAccess.bat|若要生成解决方案的大型机访问组件的批处理文件。|  
  
 中的文件\<安装目录\>\MFAccess\HISTIComponent  
  
|文件|Description|  
|----------|-----------------|  
|bizcbl.txt|若要在大型机上运行的 COBOL 程序。|  
|HISTIComponent.tiproj|事务集成器项目文件。|  
|MainFrameProgramVTCS2Description.txt|事务集成器导出文件。|  
|SOHISTIUsingCOM.TLB|类型库。|  
  
 中的文件\<安装目录\>\MFAccess\HISTISimpleTester  
  
|文件|Description|  
|----------|-----------------|  
|App.ico|图标文件|  
|AssemblyInfo.cs|程序集信息文件。|  
|Form1.cs|若要测试与大型机的连接的 Windows 窗体程序。|  
|Form1.resx|资源文件|  
|HISTISimpleTester.csproj|C#项目文件。|  
|Interop.SOHISTIUsingCOM.dll.reg|DLL 注册文件。|  
  
 中的文件\<安装目录\>\MFAccess\PendingTransactions  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|Global.asax|生成的文件。|  
|Global.asax.cs|生成的文件。|  
|Global.asax.resx|生成的文件。|  
|PendingTransactions.csproj|C#项目文件。|  
|PendingTransactions.csproj.webinfo|生成的文件。|  
|PendTransWS.asmx|生成的文件。|  
|PendTransWS.asmx.cs|生成的文件。|  
|PendTransWS.asmx.resx|生成的文件。|  
|Web.config|生成的文件。|  
  
 中的文件\<安装目录\>\MFAccess\SchemaClasses  
  
|文件|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|程序集信息文件。|  
|BAPI_BANKACCT_GET_DETAIL.cs|C#从相应的架构 (.xsd) 文件生成的类。|  
|CustomerServiceRequest.cs|C#从相应的架构 (.xsd) 文件生成的类。|  
|CustomerServiceResponse.cs|C#从相应的架构 (.xsd) 文件生成的类。|  
|LastPaymentRequest.cs|C#从相应的架构 (.xsd) 文件生成的类。|  
|LastPaymentResponse.cs|C#从相应的架构 (.xsd) 文件生成的类。|  
|PendingTransactionsRequest.cs|C#从相应的架构 (.xsd) 文件生成的类。|  
|PendingTransactionsResponse.cs|C#从相应的架构 (.xsd) 文件生成的类。|  
|SchemaClasses.csproj|C#项目文件。|  
  
## <a name="see-also"></a>请参阅  
 [面向服务的组件的解决方案](../core/components-of-the-service-oriented-solution.md)   
 [面向服务的解决方案参考](../core/service-oriented-solution-reference.md)