---
title: 面向服务的消息引用的解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, message reference
ms.assetid: 47b56d83-799d-444d-b7ef-c2db56a0e470
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79467e6e3eec6e635071c2494c5463a7e4692554
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394563"
---
# <a name="message-reference-for-the-service-oriented-solution"></a>面向服务的消息引用的解决方案
本部分列出的消息和使用的解决方案中每个业务流程的消息类型。 按应用程序的版本列出的消息和类型。  
  
## <a name="adapter-version"></a>适配器版本  
 在表中，\<前缀\>替代 Microsoft.Samples.BizTalk.WoodgroveBank，以便于表的格式。  
  
 业务流程、 消息和类型如下所示：  
  
|业务流程|消息|消息类型|  
|-------------------|-------------|------------------|  
|CustomerService.odx|LastPaymentRequest|\<SolutionPrefix\>.Schemas.LastPaymentRequest|  
|CustomerService.odx|LastPaymentResponse|\<SolutionPrefix\>.Schemas.LastPaymentResponse|  
|CustomerService.odx|PendingTransactionsWSRequest|\<SolutionPrefix\>.Orchestrations.Adapter.PendTransWS.PendingTransactionsWebService_.GetPendingTransactions_request|  
|CustomerService.odx|PendingTransactionsWSResponse|\<SolutionPrefix\>.Orchestrations.Adapter.PendTransWS.PendingTransactionsWebService_.GetPendingTransactions_response|  
|CustomerService.odx|CreditLimitRequest|\<SolutionPrefix\>.Schemas.BAPI_BANKACCT_GET_DETAIL.BAPI_BANKACCT_GET_DETAIL_Request|  
|CustomerService.odx|CreditLimitResponse|\<SolutionPrefix\>.Schemas.BAPI_BANKACCT_GET_DETAIL.BAPI_BANKACCT_GET_DETAIL_Response|  
|CustomerService.odx|PendingTransactionsRequest|\<SolutionPrefix\>.Schemas.PendingTransactionsRequest|  
|CustomerService.odx|PendingTransactionsResponse|\<SolutionPrefix\>.Schemas.PendingTransactionsResponse|  
|CustomerService.odx|StubSAPWebServiceRequest|\<SolutionPrefix\>.Orchestrations.Adapter.StubSAPWS.StubSAPWS_.GetAccountDetails_request|  
|CustomerService.odx|StubSAPWebServiceResponse|\<SolutionPrefix\>.Orchestrations.Adapter.StubSAPWS.StubSAPWS_.GetAccountDetails_response|  
|CustomerService.odx|CustomerServiceRequest|\<SolutionPrefix\>.Schemas.CustomerServiceRequest|  
|CustomerService.odx|CustomerServiceResponse|\<SolutionPrefix\>.Schemas.CustomerServiceResponse|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceRequest|\<SolutionPrefix\>.Schemas.CustomerServiceRequest|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceResponse|\<SolutionPrefix\>.Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceResponse2|\<SolutionPrefix\>.Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceResponse|\<SolutionPrefix\>.Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceRequest|\<SolutionPrefix\>.Schemas.CustomerServiceRequest|  
  
## <a name="adapter-with-sap-version"></a>与 SAP 版本的适配器  
 在表中，\<前缀\>替代 Microsoft.Samples.BizTalk.WoodgroveBank，以便于表的格式。  
  
 业务流程、 消息和类型如下所示：  
  
|业务流程|消息|消息类型|  
|-------------------|-------------|------------------|  
|CustomerService.odx|LastPaymentRequest|\<SolutionPrefix\>.Schemas.LastPaymentRequest|  
|CustomerService.odx|LastPaymentResponse|\<SolutionPrefix\>.Schemas.LastPaymentResponse|  
|CustomerService.odx|PendingTransactionsWSRequest|\<SolutionPrefix\>.Orchestrations.Adapter.PendTransWS.PendingTransactionsWebService_.GetPendingTransactions_request|  
|CustomerService.odx|PendingTransactionsWSResponse|\<SolutionPrefix\>.Orchestrations.Adapter.PendTransWS.PendingTransactionsWebService_.GetPendingTransactions_response|  
|CustomerService.odx|CreditLimitRequest|\<SolutionPrefix\>.Schemas.BAPI_BANKACCT_GET_DETAIL.BAPI_BANKACCT_GET_DETAIL_Request|  
|CustomerService.odx|CreditLimitResponse|\<SolutionPrefix\>.Schemas.BAPI_BANKACCT_GET_DETAIL.BAPI_BANKACCT_GET_DETAIL_Response|  
|CustomerService.odx|PendingTransactionsRequest|\<SolutionPrefix\>.Schemas.PendingTransactionsRequest|  
|CustomerService.odx|PendingTransactionsResponse|\<SolutionPrefix\>.Schemas.PendingTransactionsResponse|  
|CustomerService.odx|CustomerServiceRequest|\<SolutionPrefix\>.Schemas.CustomerServiceRequest|  
|CustomerService.odx|CustomerServiceResponse|\<SolutionPrefix\>.Schemas.CustomerServiceResponse|  
  
## <a name="inline-version"></a>内联版本  
 在表中，\<前缀\>替代 Microsoft.Samples.BizTalk.WoodgroveBank，以便在表的格式设置。  
  
 业务流程、 消息和类型如下所示：  
  
|业务流程|消息|消息类型|  
|--------------------|-------------|------------------|  
|CustomerService.odx|LastPaymentRequest|\<SolutionPrefix\>.Schemas.LastPaymentRequest|  
|CustomerService.odx|LastPaymentResponse|\<SolutionPrefix\>.Schemas.LastPaymentResponse|  
|CustomerService.odx|PendingTransactionsWSRequest|\<SolutionPrefix\>.Schemas.PendingTransactionsRequest|  
|CustomerService.odx|PendingTransactionsWSResponse|\<SolutionPrefix\>.Schemas.PendingTransactionsResponse|  
|CustomerService.odx|CreditLimitRequest|\<SolutionPrefix\>.Schemas.BAPI_BANKACCT_GET_DETAIL.BAPI_BANKACCT_GET_DETAIL_Request|  
|CustomerService.odx|CreditLimitResponse|\<SolutionPrefix\>.Schemas.BAPI_BANKACCT_GET_DETAIL.BAPI_BANKACCT_GET_DETAIL_Response|  
|CustomerService.odx|LastPaymentRequestAfterSendPipeline|System.Xml.XmlDocument|  
|CustomerService.odx|LastPaymentResponseBeforeReceivePipeline|System.Xml.XmlDocument|  
|CustomerService.odx|CustomerServiceRequest|\<SolutionPrefix\>.Schemas.CustomerServiceRequest|  
|CustomerService.odx|CustomerServiceResponse|\<SolutionPrefix\>.Schemas.CustomerServiceResponse|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceRequest|\<SolutionPrefix\>.Schemas.CustomerServiceRequest|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceResponse|\<SolutionPrefix\>.Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceResponse2|\<SolutionPrefix\>.Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceResponse|\<SolutionPrefix\>.Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceRequest|\<SolutionPrefix\>.Schemas.CustomerServiceRequest|  
  
## <a name="stub-version"></a>存根版本  
 在表中，\<前缀\>替代 Microsoft.Samples.BizTalk.WoodgroveBank，以便在表的格式设置。  
  
 业务流程、 消息和类型如下所示：  
  
|业务流程|消息|消息类型|  
|-------------------|-------------|------------------|  
|CustomerService.odx|LastPaymentRequest|\<SolutionPrefix\>.Schemas.LastPaymentRequest|  
|CustomerService.odx|LastPaymentResponse|\<SolutionPrefix\>.Schemas.LastPaymentResponse|  
|CustomerService.odx|PendingTransactionsWSRequest|\<SolutionPrefix\>.Orchestrations.Stubbed.StubPendTransWS.StubPendingTransactionsWebService_.GetPendingTransactions_request|  
|CustomerService.odx|PendingTransactionsWSResponse|\<SolutionPrefix\>.Orchestrations.Stubbed.StubPendTransWS.StubPendingTransactionsWebService_.GetPendingTransactions_response|  
|CustomerService.odx|CreditLimitRequest|\<SolutionPrefix\>.Schemas.BAPI_BANKACCT_GET_DETAIL.BAPI_BANKACCT_GET_DETAIL_Request|  
|CustomerService.odx|CreditLimitResponse|\<SolutionPrefix\>.Schemas.BAPI_BANKACCT_GET_DETAIL.BAPI_BANKACCT_GET_DETAIL_Response|  
|CustomerService.odx|PendingTransactionsRequest|\<SolutionPrefix\>.Schemas.PendingTransactionsRequest|  
|CustomerService.odx|PendingTransactionsResponse|\<SolutionPrefix\>.Schemas.PendingTransactionsResponse|  
|CustomerService.odx|PaymentTrackerWSRequest|\<SolutionPrefix\>.Orchestrations.Stubbed.StubPmntTrckWS.StubPaymentTrackerWebService_.GetLastPayments_request|  
|CustomerService.odx|PaymentTrackerWSResponse|\<SolutionPrefix\>.Orchestrations.Stubbed.StubPmntTrckWS.StubPaymentTrackerWebService_.GetLastPayments_response|  
|CustomerService.odx|StubSAPWSRequest|\<SolutionPrefix\>.Orchestrations.Stubbed.StubSAPWS.StubSAPWS_.GetAccountDetails_request|  
|CustomerService.odx|StubSAPWSResponse|\<SolutionPrefix\>.Orchestrations.Stubbed.StubSAPWS.StubSAPWS_.GetAccountDetails_response|  
|CustomerService.odx|CustomerServiceRequest|\<SolutionPrefix\>.Schemas.CustomerServiceRequest|  
|CustomerService.odx|CustomerServiceResponse|\<SolutionPrefix\>.Schemas.CustomerServiceResponse|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceRequest|\<SolutionPrefix\>.Schemas.CustomerServiceRequest|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceResponse|\<SolutionPrefix\>.Schemas.CustomerServiceResponse|  
  
## <a name="see-also"></a>请参阅  
 [面向服务的解决方案参考](../core/service-oriented-solution-reference.md)