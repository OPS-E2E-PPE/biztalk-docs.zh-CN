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
ms.openlocfilehash: 313bfb773a94914ed9bebd3930dfd0033ecf4ac3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="publishing-from-the-biztalk-server-administration-console"></a><span data-ttu-id="9d0a5-102">从 BizTalk Server 管理控制台发布</span><span class="sxs-lookup"><span data-stu-id="9d0a5-102">Publishing from the BizTalk Server Administration Console</span></span>
<span data-ttu-id="9d0a5-103">如果你想要管理通过终结点发布[!INCLUDE[prague](../includes/prague-md.md)]而不是 ESB 管理门户管理控制台中，你可以做到这一点在的说明字段中输入一个通用、 描述、 发现和集成 (UDDI) 的名字对象若要将发布到 UDDI 的终结点。</span><span class="sxs-lookup"><span data-stu-id="9d0a5-103">If you want to manage endpoint publishing through the [!INCLUDE[prague](../includes/prague-md.md)] Administration Console instead of the ESB Management Portal, you can do so by entering a Universal Description, Discovery, and Integration (UDDI) moniker in the description field of the endpoints to publish to UDDI.</span></span> <span data-ttu-id="9d0a5-104">下面是示例标记。</span><span class="sxs-lookup"><span data-stu-id="9d0a5-104">The following is an example moniker.</span></span>  
  
```  
uddi://TransportType=other;Status=Published.  
```  
  
 <span data-ttu-id="9d0a5-105">你可以设置以下 UDDI 属性使用**说明**字段[!INCLUDE[prague](../includes/prague-md.md)]管理控制台：</span><span class="sxs-lookup"><span data-stu-id="9d0a5-105">You can set the following UDDI properties using the **Description** field in the [!INCLUDE[prague](../includes/prague-md.md)] Administration Console:</span></span>  
  
-   <span data-ttu-id="9d0a5-106">**ModifiedBy**。</span><span class="sxs-lookup"><span data-stu-id="9d0a5-106">**ModifiedBy**.</span></span> <span data-ttu-id="9d0a5-107">此可选属性包含的用户的修改终结点，该帐户名例如，MyDomainName\MyUserName。</span><span class="sxs-lookup"><span data-stu-id="9d0a5-107">This optional property contains the account name of the user that modified the endpoint; for example, MyDomainName\MyUserName.</span></span>  
  
-   <span data-ttu-id="9d0a5-108">**UDDIContact**。</span><span class="sxs-lookup"><span data-stu-id="9d0a5-108">**UDDIContact**.</span></span> <span data-ttu-id="9d0a5-109">此可选属性是为 UDDI 业务提供程序定义的用户的联系人姓名。</span><span class="sxs-lookup"><span data-stu-id="9d0a5-109">This optional property is the contact name of the user defined for the UDDI Business Provider.</span></span>  
  
-   <span data-ttu-id="9d0a5-110">**UDDIUserType**。</span><span class="sxs-lookup"><span data-stu-id="9d0a5-110">**UDDIUserType**.</span></span> <span data-ttu-id="9d0a5-111">此可选属性是用户定义 UDDI 业务提供程序的用户类型。</span><span class="sxs-lookup"><span data-stu-id="9d0a5-111">This optional property is the user type of the user defined for the UDDI Business Provider.</span></span>  
  
-   <span data-ttu-id="9d0a5-112">**UDDIEmail**。</span><span class="sxs-lookup"><span data-stu-id="9d0a5-112">**UDDIEmail**.</span></span> <span data-ttu-id="9d0a5-113">此可选属性是为 UDDI 业务提供程序定义的用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="9d0a5-113">This optional property is the e-mail address of the user defined for the UDDI Business Provider.</span></span>  
  
-   <span data-ttu-id="9d0a5-114">**TransportType**。</span><span class="sxs-lookup"><span data-stu-id="9d0a5-114">**TransportType**.</span></span> <span data-ttu-id="9d0a5-115">此可选属性是终结点适配器类型，如**文件、 MQS、 WCF WsHttp、 SOAP、 HTTP、**或**FTP**。</span><span class="sxs-lookup"><span data-stu-id="9d0a5-115">This optional property is the endpoint adapter type, such as **FILE, MQS, WCF-WsHttp, SOAP, HTTP,** or **FTP**.</span></span>  
  
-   <span data-ttu-id="9d0a5-116">**状态**。</span><span class="sxs-lookup"><span data-stu-id="9d0a5-116">**Status**.</span></span> <span data-ttu-id="9d0a5-117">此可选属性是，终结点的状态，如**已发布**或**挂起**。</span><span class="sxs-lookup"><span data-stu-id="9d0a5-117">This optional property is the status of the endpoint, such as **Published** or **Pending**.</span></span> <span data-ttu-id="9d0a5-118">UDDI 发布服务使用此属性来发现终结点的状态。</span><span class="sxs-lookup"><span data-stu-id="9d0a5-118">The UDDI Publishing Service uses this attribute to discover the status of the endpoint.</span></span>  
  
-   <span data-ttu-id="9d0a5-119">**BindingType**。</span><span class="sxs-lookup"><span data-stu-id="9d0a5-119">**BindingType**.</span></span> <span data-ttu-id="9d0a5-120">此可选属性是特定的协议 （URL 类型） UDDI 绑定支持，如**mailto，http、 https、 ftp、 传真、 phone**或**其他**。</span><span class="sxs-lookup"><span data-stu-id="9d0a5-120">This optional property is the specific protocol (URL Type) that the UDDI binding supports, such as **mailto, http, https, ftp, fax, phone,** or **other**.</span></span> <span data-ttu-id="9d0a5-121">UDDI 发布服务使用此属性来创建终结点绑定。</span><span class="sxs-lookup"><span data-stu-id="9d0a5-121">The UDDI Publishing Service uses this attribute to create the endpoint binding.</span></span>