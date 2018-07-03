---
title: 教程 5： 调用 REST 接口使用 BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73871ca3-abd0-45ae-b379-6df76a967a80
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d45daa5f567863fd3531edb1f951ac673628fd6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967566"
---
# <a name="tutorial-5-invoking-a-rest-interface-using-biztalk-server"></a>教程 5： 调用 REST 接口使用 BizTalk Server
本部分提供了有关如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 调用 REST 终结点的分步概览。 在本教程中，你将调用 [!INCLUDE[winazure](../includes/winazure-md.md)] 市场中的 REST 终结点，该终结点将返回美国航空公司航班的延误情况。 本教程使用的新**Wcf-webhttp**适配器中引入[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来调用 REST 终结点。  
  
##  <a name="BKMK_Scenario"></a> 本教程中使用的方案  
 
  [!INCLUDE[winazure](../includes/winazure-md.md)] 市场提供了以下 REST 资源 URL 来检索美国航空公司航班的延误情况：  
  
```  
https://api.datamarket.azure.com/oakleaf/US_Air_Carrier_Flight_Delays_Incr/On_Time_Performance  
```  
  
 如果在 Web 浏览器的地址栏中输入此 URL，系统会提示你输入访问资源的凭据。 登录到之后[Windows Azure Marketplace](http://go.microsoft.com/fwlink/p/?LinkId=257913)，你可以获取从凭据**我的帐户**web 页的选项卡。 对列出这些凭据**Customer ID** （用户名） 和**主帐户密钥**（密码） 标签。  
  
 在本教程中，将使用的资源 URL 和凭据来配置一个双向**Wcf-webhttp**发送端口。 该双向发送端口的接收管道将接收包含航班详细信息的响应消息，然后将其发布到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MessageBox 数据库。 你将配置一个 FILE 发送端口，以便订阅由 WCF-WebHttp 发送端口发布的所有消息。 该 FILE 发送端口将处理来自 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的消息，然后将其复制到某个文件位置。  
  
 在现实世界的业务场合中，可以通过将 WCF-WebHttp 发送端口与某个大型业务流程（如从业务应用程序获取消息的接收位置）关联来触发该发送端口。 但是，在本教程中，由于重点是演示如何调用 REST 接口，因此你可以使用一个接收虚拟消息的简单 FILE 位置来触发该发送端口。  
  
 因此，总体而言，你必须执行以下步骤来配置此解决方案：  
  
1.  配置一个 FILE 接收位置来提取虚拟请求消息。  
  
2.  配置一个双向 WCF-WebHttp 发送端口来调用 REST 资源 URL 并接收响应。  
  
3.  配置一个单向 FILE 发送端口来处理包含航班详细信息的响应消息，然后将其复制到某个文件位置。  
  
## <a name="set-up-your-includewinazureincludeswinazure-mdmd-marketplace-account"></a>设置 [!INCLUDE[winazure](../includes/winazure-md.md)] 市场帐户  
 若要访问通过 REST 终结点公开的航班延误数据，必须首先订阅美国航空公司航班延误示例数据源。 执行以下步骤来执行此操作：  
  
#### <a name="to-subscribe-to-the-data-feed"></a>订阅数据源  
  
1. 使用你的 Microsoft 帐户登录到 [!INCLUDE[winazure](../includes/winazure-md.md)] 市场。  
  
2. 在中**数据**选项卡上，找到并单击**美国美国航空公司航班延误**服务。  
  
3. 在数据服务页面上单击**注册**。 在注册页上，接受协议的条款，然后单击**注册**试。  
  
4. 在中**我的帐户**选项卡上，检索用于访问数据服务的凭据。 对列出这些凭据**Customer ID** （用户名） 和**主帐户密钥**（密码） 标签。 配置时，将需要这些凭据**Wcf-webhttp**发送端口。  
  
## <a name="set-up-your-computer"></a>设置计算机  
 若要配置本教程中使用的方案，你必须在自己的计算机上安装和配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 如果想要预配[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机上 Windows Azure VM，请遵循的说明[Azure VM 上配置 BizTalk Server](http://msdn.microsoft.com/library/azure/jj248689.aspx)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1：配置 FILE 接收位置](../core/step-1-configure-a-file-receive-location.md)  
  
-   [步骤 2：配置双向 WCF-WebHttp 发送端口](../core/step-2-configure-a-two-way-wcf-webhttp-send-port.md)  
  
-   [步骤 3：配置单向 FILE 发送端口](../core/step-3-configure-a-one-way-file-send-port.md)  
  
-   [步骤 4：测试解决方案](../core/step-4-test-the-solution.md)