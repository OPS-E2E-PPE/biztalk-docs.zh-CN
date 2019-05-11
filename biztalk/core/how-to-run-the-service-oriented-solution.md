---
title: 如何运行该服务面向解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, client applications
- service solution tutorial, starting solution
- service solution tutorial, sending requests
- service solution tutorial, SOAP transports
ms.assetid: 764a5ddc-e571-41d8-9e2f-6d0fb3361b2f
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8aa1fed4a695eef0e21a3199854416436bf2af13
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384074"
---
# <a name="how-to-run-the-service-oriented-solution"></a>如何运行该服务面向解决方案
以下步骤介绍如何运行和验证面向服务的解决方案在单台计算机上。 启动付款跟踪模拟程序之后, 可以发送请求使用 SOAP 或 MQSeries 传输 （具有单独的适配器版本和内联版本的面向服务的解决方案的过程）。  
  
-   [通过使用客户端应用程序 （存根版本） 的 SOAP 传输发送请求](#step1)  
  
-   [使用客户端应用程序 （适配器版本） 发送请求](#step3)  
  
-   [使用客户端应用程序 （内联版本） 发送请求](#step5)  
  
##  <a name="step1"></a> 通过使用客户端应用程序 （存根版本） 的 SOAP 传输发送请求  
  
#### <a name="to-send-requests-by-soap-transport-using-the-client-application-stub-version"></a>若要通过使用客户端应用程序 （存根版本） 的 SOAP 传输发送请求  
  
1.  打开命令提示符下，将目录更改为\< *BizTalk Server 安装目录*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release，，然后运行 BTSScnSOSimpleClient.exe。  
  
2.  中键入任意字符**RequestType**， **RequestSource**，并**RequestID**文本框。  
  
3.  键入在任何 16 位数字**帐号**文本框。  
  
4.  选择**SOAP （WS 调用）** 并**存根**中**选择传输和参数**分组框。  
  
5.  键入以下 URL 中的**URL**文本框中，例如：  
  
6.  `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub/CustomerServicePort.asmx`  
  
7.  类型`ZipCode`中**名称**下的文本框**身份验证元素**，然后键入中的任何字符**值**文本框。  
  
8.  类型`CustomerName`中**名称**下的文本框**身份验证元素**，然后键入中的任何字符**值**文本框。  
  
9. 单击**获取余额**。  
  
10. 响应显示在**响应**文本框中：**成功**显示如果请求已成功处理; 如果请求失败，将显示一条错误消息。  
  
     ![运行用于存根版本的客户端应用程序](../core/media/bts-cp-so-deploy-stubversion-success.gif "BTS_CP_SO_Deploy_StubVersion_Success")  
  
##  <a name="step3"></a> 使用客户端应用程序 （适配器版本） 发送请求  
  
#### <a name="to-send-requests-using-the-client-application-adapter-version"></a>若要使用客户端应用程序 （适配器版本） 发送请求  
  
1.  打开命令提示符下，将目录更改为\< *BizTalk Server 安装目录*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug，然后运行以下命令以启动付款跟踪模拟程序：  
  
     `BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <` *队列管理器名称* `> 5 [<` *通道定义* `>]`  
  
    > [!NOTE]
    >  通道定义是可选的如果它不是远程 MQSeries 服务器。  
  
    -   将付款跟踪模拟程序运行。  
  
2.  打开命令提示符下，将目录更改为\< *BizTalk Server 安装目录*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release，，然后运行 BTSScnSOSimpleClient.exe。  
  
3.  在 BTSScnSOSimpleClient.exe 中发送 soap 请求传输如下所示：  
  
    1.  中键入任意字符**RequestType**， **RequestSource**，并**RequestID**文本框。  
  
    2.  键入在任何 16 位数字**帐号**文本框。  
  
    3.  选择**SOAP （WS 调用）** 并**适配器**中**选择传输和参数**分组框。  
  
    4.  键入以下 URL 中的**URL**文本框中，例如：  
  
         `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter/CustomerServicePort.asmx`  
  
    5.  类型`ZipCode`中**名称**下的文本框**身份验证元素**，然后键入中的任何字符**值**文本框。  
  
    6.  类型`CustomerName`中**名称**下的文本框**身份验证元素**，然后键入中的任何字符**值**文本框。  
  
    7.  单击**获取余额**。  
  
    8.  响应显示在**响应**文本框中：**成功**显示如果请求已成功处理; 如果请求失败，将显示一条错误消息。  
  
         ![运行用于适配器版本的客户端应用程序](../core/media/soap-transport-adapter-success.gif "SOAP_Transport_adapter_success")  
  
4.  在 BTSScnSOSimpleClient.exe 中通过传输发送请求 MQSeries，如下所示：  
  
    1.  中键入任意字符**RequestType**， **RequestSource**，并**RequestID**文本框。  
  
    2.  键入在 16 位数字**帐号**文本框。  
  
    3.  选择**MQSeries**中**选择传输和参数**分组框。  
  
    4.  类型\<*队列管理器名称*\>中**队列管理器**文本框。 QM_\<*您的计算机名称*\>是默认值\<*队列管理器名称*\>。  
  
    5.  类型`AdapterSOAInputQueue`中**输入队列**文本框。  
  
    6.  类型`AdapterSOAOutputQueue`中**输出队列**文本框。  
  
    7.  类型\<*通道定义*\>中**通道定义**框。 S_\<*您的计算机名称*\>/tcp/&lt\<*您的计算机名称*\>(1414) 是默认值为\< *通道定义*\>。  
  
    8.  类型`ZipCode`中**名称**下的文本框**身份验证元素**，然后键入中的任何字符**值**文本框。  
  
    9. 类型`CustomerName`中**名称**下的文本框**身份验证元素**，然后键入中的任何字符**值**文本框。  
  
    10. 单击**获取余额**。  
  
    11. 响应显示在**响应**文本框中：**成功**显示如果请求已成功处理; 如果请求失败，将显示一条错误消息。  
  
         ![运行用于适配器版本的客户端应用程序](../core/media/mqseries-transport-adapter.gif "MQSeries_Transport_adapter")  
  
##  <a name="step5"></a> 使用客户端应用程序 （内联版本） 发送请求  
  
#### <a name="to-send-requests-using-the-client-application-inline-version"></a>若要使用客户端应用程序 （内联版本） 发送请求  
  
1.  打开命令提示符下，将目录更改为\< *BizTalk Server 安装目录*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug，并运行以下命令以启动付款跟踪模拟程序：  
  
     `BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <` *队列管理器名称* `> 5 [<` *通道定义* `>]`  
  
    > [!NOTE]
    >  通道定义是可选的如果它不是远程 MQSeries 服务器。  
  
    > [!NOTE]
    >  如果付款跟踪模拟程序已在运行，请跳过此步骤。  
  
    -   将付款跟踪模拟程序运行。  
  
2.  在中**BizTalk Server 管理控制台**，展开**BTSScn.SO.CustomerService**，单击**接收位置**，右键单击**PaymentTrackingSystemOutputQueue**在右窗格中，然后单击**禁用**。  
  
    > [!NOTE]
    >  适配器版本和内联版本使用同一个 MQSeries 队列，即 LastPaymentsOutputQueue。 若要避免两个版本之间的争用条件，请禁用适配器版本的接收位置 MQSeries 队列上侦听。  
  
3.  打开命令提示符下，将目录更改为\< *BizTalk Server 安装目录*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release，，然后运行 BTSScnSOSimpleClient.exe。  
  
4.  在 BTSScnSOSimpleClient.exe 中发送 soap 请求传输如下所示：  
  
    1.  中键入任意字符**RequestType**， **RequestSource**，并**RequestID**文本框。  
  
    2.  键入在任何 16 位数字**帐号**文本框。  
  
    3.  选择**SOAP （WS 调用）** 并**内联**中**选择传输和参数**分组框。  
  
    4.  键入以下 URL 中的**URL**文本框中，例如：  
  
         `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline/CustomerServicePort.asmx`  
  
    5.  类型`ZipCode`中**名称**下的文本框**身份验证元素**，然后键入中的任何字符**值**文本框。  
  
    6.  类型`CustomerName`中**名称**下的文本框**身份验证元素**，然后键入中的任何字符**值**文本框。  
  
    7.  单击**获取余额**。  
  
    8.  响应显示在**响应**文本框中：**成功**显示如果请求已成功处理; 如果请求失败，将显示一条错误消息。  
  
         ![运行用于内联版本的客户端应用程序](../core/media/soap-transport-inline.gif "SOAP_Transport_inline")  
  
5.  在 BTSScnSOSimpleClient.exe 中通过传输发送请求 MQSeries，如下所示：  
  
    1.  中键入任意字符**RequestType**， **RequestSource**，并**RequestID**文本框。  
  
    2.  键入在 16 位数字**帐号**文本框。  
  
    3.  选择**MQSeries**中**选择传输和参数**分组框。  
  
    4.  类型\<*队列管理器名称*\>中**队列管理器**文本框。 QM_\<*您的计算机名称*\>是默认值\<*队列管理器名称*\>。  
  
    5.  类型`InlineSOAInputQueue`中**输入队列**文本框。  
  
    6.  类型`InlineSOAOutputQueue`中**输出队列**文本框。  
  
    7.  类型\<*通道定义*\>中**通道定义**框。 S_\<*您的计算机名称*\>/tcp/&lt\<*您的计算机名称*\>(1414) 是默认值为\< *通道定义*\>。  
  
    8.  类型`ZipCode`中**名称**下的文本框**身份验证元素**，然后键入中的任何字符**值**文本框。  
  
    9. 类型`CustomerName`中**名称**下的文本框**身份验证元素**，然后键入中的任何字符**值**文本框。  
  
    10. 单击**获取余额**。  
  
    11. 响应显示在**响应**文本框中：**成功**显示如果请求已成功处理; 如果请求失败，将显示一条错误消息。  
  
         ![运行用于内联版本的客户端应用程序](../core/media/mqseries-transport-inline.gif "MQSeries_Transport_inline")  
  
## <a name="see-also"></a>请参阅  
 [然后再安装面向服务的解决方案](../core/before-installing-the-service-oriented-solution.md)   
 [如何安装该服务的存根版本面向解决方案](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md)   
 [如何安装的内联版本和适配器版本的服务面向解决方案](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)   
 [面向服务的解决方案的开发人员计算机设置](../core/developer-machine-setup-for-the-service-oriented-solution.md)