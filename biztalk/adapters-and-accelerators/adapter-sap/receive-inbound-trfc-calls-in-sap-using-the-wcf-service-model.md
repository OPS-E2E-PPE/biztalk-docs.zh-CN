---
title: 在使用 WCF 服务模型的 SAP 中收到入站的 tRFC 调用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tRFC calls, receiving inbound using the WCF service model
- WCF service model, receiving inbound tRFC calls
ms.assetid: 02dc282b-b659-466a-8bd1-f400a05f71ec
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd54bdfd3a772912b4d2687ab1ce9e715e7fbab9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013326"
---
# <a name="receive-inbound-trfc-calls-in-sap-using-the-wcf-service-model"></a>在使用 WCF 服务模型的 SAP 中收到入站的 tRFC 调用
可以使用[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]作为事务的 RFC (tRFC) 服务器以接收来自 SAP 的入站的 tRFC 调用。 对于入站 Trfc[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持多个 Trfc 中的工作 (LUW) 相同的 SAP 逻辑单元。  
  
 本主题中的部分提供有关如何使用适配器为 WCF 服务模型中的 tRFC 服务器信息。  
  
 你可以找到有关使用的详细信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]为 tRFC 服务器中的以下主题：  
  
- 有关对 Trfc 上支持的概述[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[Trfc 在 SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)。 在继续之前，应阅读本主题。  
  
- TRFC 服务器操作的消息架构的详细信息，请参阅[Trfc 在 SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)。  
  
## <a name="the-wcf-service-contract-for-a-trfc"></a>TRFC WCF 服务约定  
 您使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel Metadata Utility Tool (svcutil.exe) 来生成你想要接收来自 SAP 系统的 Trfc 的 WCF 服务约定。 为入站的 tRFC 是类似于为入站 RFC 生成生成的协定，只不过：  
  
- tRFC 操作 TRFC 节点下显示。  
  
- WCF 服务协定 （接口） 为传入 Trfc 生成名为"Trfc"。 将服务终结点添加到服务主机时，必须指定此接口。 这也是您的 WCF 服务必须实现的接口。  
  
  ```  
  public interface Trfc {  
  
      // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.Sap/2007/03/Trfc/) of message Z_RFC_MKD_ADDRequest does not match the default value (http://Microsoft.LobServices.Sap/2007/03/)  
      [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.LobServices.Sap/2007/03/Trfc/Z_RFC_MKD_ADD", ReplyAction="http://Microsoft.LobServices.Sap/2007/03/Trfc/Z_RFC_MKD_ADD/response")]  
      Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request);  
  }  
  ```  
  
- TRFC 操作的请求消息约定有一个 GUID 参数。 这是映射到 SAP TID trfc 的 GUID。 TRFC 服务器操作，在适配器管理提交、 回滚，并确认 TID 由 SAP 系统，因此没有任何理由要求您显式地使用此 GUID 的所有调用。 但是，可以使用它来检索从 SAP TID[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]通过调用**SapAdapterUtilities.ConvertGuidToTid**。 这可用于帮助你排查上的 SAP 系统的问题。  
  
  ```  
  [System.Diagnostics.DebuggerStepThroughAttribute()]  
  [System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
  [System.ServiceModel.MessageContractAttribute(WrapperName="Z_RFC_MKD_ADD", WrapperNamespace="http://Microsoft.LobServices.Sap/2007/03/Trfc/", IsWrapped=true)]  
  public partial class Z_RFC_MKD_ADDRequest {  
  
      ...  
  
      public Z_RFC_MKD_ADDRequest(string DEST, System.Nullable<int> X, System.Nullable<int> Y, System.Guid TransactionalRfcOperationIdentifier) {  
          this.DEST = DEST;  
          this.X = X;  
          this.Y = Y;  
          this.TransactionalRfcOperationIdentifier = TransactionalRfcOperationIdentifier;  
      }  
  }  
  
  ```  
  
## <a name="how-do-i-enable-the-adapter-to-act-as-a-trfc-server"></a>如何启用到 Act 适配器作为 tRFC 服务器？  
 若要启用适配器为 tRFC 服务器，必须设置**TidDatabaseConnectionString**属性绑定到 TID 数据库的连接字符串。 在打开服务主机之前应执行此操作。 这是适配器将在其中存储每个 tRFC SAP 事务 ID (TID) 的数据库。 有关此绑定属性的详细信息，请参阅[了解用于 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
## <a name="how-do-i-enlist-in-the-transaction-for-inbound-trfcs"></a>如何在入站 Trfc 的事务中登记？  
 SAP 逻辑单元的工作 (LUW) 可以包含多个 Trfc。 SAP 系统上 LUW 标识的唯一事务 ID (TID)。 适配器为每个 SAP 系统时它将调用 tRFC 调用在适配器上的使用 Tid 创建可提交的事务。 SAP 系统时调用适配器; 上 tRFC该适配器的流与 SAP TID 到你的服务关联的事务。 在操作方法，可以访问此事务中的环境事务。 在此环境事务中登记，通过在操作中所执行的操作可以参与 SAP LUW。  
  
 若要在操作方法中的环境事务中登记，必须：  
  
1. 将操作方法使用批注**TransactionScopeRequired**的属性**OperationBehavior**属性。 这将告知 WCF 希望从操作中的环境事务访问。  
  
2. 通过使用操作方法创建一个事务范围**TransactionAutoComplete**的属性**OperationBehavior**属性或通过显式使用**TransactionScope**在操作方法。  
  
   下面的示例演示实现两个操作的服务。 这两种操作方法使用批注**TransactionScopeRequired**属性来访问环境事务。  
  
-   **Z_TRFC_EXAMPLE1**显式使用在事务中登记**TransactionScope**对象。  
  
-   **Z_TRFC_EXAMPLE2**使用批注**TransactionAutoComplete**属性在事务中登记  
  
```  
[ServiceBehavior(InstanceContextMode = InstanceContextMode.Single, UseSynchronizationContext = false)]  
class Z_Example_ServiceContractClass : Trfc  
{  
  
    // This operation method explicitly creates a TransactionScope to enlist in the ambient transaction  
    // You must explictly call ts.Complete to complete the transaction before you return from the operation  
    // Otherwise the transaction is aborted.  
    // You can throw an exception or return without calling ts.complete to abort the transacation  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public Z_TRFC_EXAMPLE1Response Z_TRFC_EXAMPLE1(Z_TRFC_EXAMPLE1Request request)  
    {  
        using (TransactionScope ts = new TransactionScope(TransactionScopeOption.Required))  
        {  
            // Process tRFC  
  
            ...  
  
            Z_TRFC_EXAMPLE1Response response = new Z_TRFC_EXAMPLE1Response();  
            response.TransactionalRfcOperationIdentifier = request.TransactionalRfcOperationIdentifier;  
            return response;  
            //since there is no ts.Complete(), this is equivalent to a rollback.  
        }  
    }  
  
    // This operation method sets the TransactionAutoComplete property of the OperationBehavior attribute  
    // to enlist in the transaction. There is no need to explictly create a TransactionScope in the code.  
    // If the method returns with no unhandled exceptions, the transaction completes; otherwise it aborts  
    // You can throw an exception to abort the transaction.  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
    public Z_TRFC_EXAMPLE2Response Z_TRFC_EXAMPLE2(Z_TRFC_EXAMPLE2Request request)  
    {  
        // Process tRFC  
  
        ...  
  
        Z_TRFC_EXAMPLE2Response response = new Z_TRFC_EXAMPLE2Response();  
        response.TransactionalRfcOperationIdentifier = request.TransactionalRfcOperationIdentifier;  
        return response;  
        //if there is no unhandled exception, the transaction completes when the operation returns.  
    }  
}  
```  
  
## <a name="see-also"></a>请参阅  
[使用 WCF 服务模型开发应用程序](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)