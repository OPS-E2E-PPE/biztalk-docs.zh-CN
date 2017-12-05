---
title: "从 BizTalk Server 管理控制台发布 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b78b1981-b227-4cf5-9435-6fc57963552a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbe03b1a8df67581ce73db31cd5ed4b80b7a109c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="publishing-from-the-biztalk-server-administration-console"></a><span data-ttu-id="661ef-102">从 BizTalk Server 管理控制台发布</span><span class="sxs-lookup"><span data-stu-id="661ef-102">Publishing from the BizTalk Server Administration Console</span></span>
<span data-ttu-id="661ef-103">如果你想要管理 BizTalk Server 管理控制台，而不是 ESB 管理门户通过发布的终结点，你可以做到这一点的终结点的说明字段中输入通用、 描述、 发现和集成 (UDDI) 名字对象若要将发布到 UDDI。</span><span class="sxs-lookup"><span data-stu-id="661ef-103">If you want to manage endpoint publishing through the BizTalk Server Administration Console instead of the ESB Management Portal, you can do so by entering a Universal Description, Discovery, and Integration (UDDI) moniker in the description field of the endpoints to publish to UDDI.</span></span> <span data-ttu-id="661ef-104">下面是示例标记。</span><span class="sxs-lookup"><span data-stu-id="661ef-104">The following is an example moniker.</span></span>  
  
```  
uddi://TransportType=other;Status=Published.  
```  
  
 <span data-ttu-id="661ef-105">你可以设置以下 UDDI 属性使用**说明**字段在 BizTalk Server 管理控制台：</span><span class="sxs-lookup"><span data-stu-id="661ef-105">You can set the following UDDI properties using the **Description** field in the BizTalk Server Administration Console:</span></span>  
  
-   <span data-ttu-id="661ef-106">**ModifiedBy**。</span><span class="sxs-lookup"><span data-stu-id="661ef-106">**ModifiedBy**.</span></span> <span data-ttu-id="661ef-107">此可选属性包含的用户的修改终结点，该帐户名例如，MyDomainName\MyUserName。</span><span class="sxs-lookup"><span data-stu-id="661ef-107">This optional property contains the account name of the user that modified the endpoint; for example, MyDomainName\MyUserName.</span></span>  
  
-   <span data-ttu-id="661ef-108">**UDDIContact**。</span><span class="sxs-lookup"><span data-stu-id="661ef-108">**UDDIContact**.</span></span> <span data-ttu-id="661ef-109">此可选属性是为 UDDI 业务提供程序定义的用户的联系人姓名。</span><span class="sxs-lookup"><span data-stu-id="661ef-109">This optional property is the contact name of the user defined for the UDDI Business Provider.</span></span>  
  
-   <span data-ttu-id="661ef-110">**UDDIUserType**。</span><span class="sxs-lookup"><span data-stu-id="661ef-110">**UDDIUserType**.</span></span> <span data-ttu-id="661ef-111">此可选属性是用户定义 UDDI 业务提供程序的用户类型。</span><span class="sxs-lookup"><span data-stu-id="661ef-111">This optional property is the user type of the user defined for the UDDI Business Provider.</span></span>  
  
-   <span data-ttu-id="661ef-112">**UDDIEmail**。</span><span class="sxs-lookup"><span data-stu-id="661ef-112">**UDDIEmail**.</span></span> <span data-ttu-id="661ef-113">此可选属性是为 UDDI 业务提供程序定义的用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="661ef-113">This optional property is the e-mail address of the user defined for the UDDI Business Provider.</span></span>  
  
-   <span data-ttu-id="661ef-114">**TransportType**。</span><span class="sxs-lookup"><span data-stu-id="661ef-114">**TransportType**.</span></span> <span data-ttu-id="661ef-115">此可选属性是终结点适配器类型，如**文件、 MQS、 WCF WsHttp、 SOAP、 HTTP、**或**FTP**。</span><span class="sxs-lookup"><span data-stu-id="661ef-115">This optional property is the endpoint adapter type, such as **FILE, MQS, WCF-WsHttp, SOAP, HTTP,** or **FTP**.</span></span>  
  
-   <span data-ttu-id="661ef-116">**状态**。</span><span class="sxs-lookup"><span data-stu-id="661ef-116">**Status**.</span></span> <span data-ttu-id="661ef-117">此可选属性是，终结点的状态，如**已发布**或**挂起**。</span><span class="sxs-lookup"><span data-stu-id="661ef-117">This optional property is the status of the endpoint, such as **Published** or **Pending**.</span></span> <span data-ttu-id="661ef-118">UDDI 发布服务使用此属性来发现终结点的状态。</span><span class="sxs-lookup"><span data-stu-id="661ef-118">The UDDI Publishing Service uses this attribute to discover the status of the endpoint.</span></span>  
  
-   <span data-ttu-id="661ef-119">**BindingType**。</span><span class="sxs-lookup"><span data-stu-id="661ef-119">**BindingType**.</span></span> <span data-ttu-id="661ef-120">此可选属性是特定的协议 （URL 类型） UDDI 绑定支持，如**mailto，http、 https、 ftp、 传真、 phone**或**其他**。</span><span class="sxs-lookup"><span data-stu-id="661ef-120">This optional property is the specific protocol (URL Type) that the UDDI binding supports, such as **mailto, http, https, ftp, fax, phone,** or **other**.</span></span> <span data-ttu-id="661ef-121">UDDI 发布服务使用此属性来创建终结点绑定。</span><span class="sxs-lookup"><span data-stu-id="661ef-121">The UDDI Publishing Service uses this attribute to create the endpoint binding.</span></span>