---
title: 从 BizTalk Server 管理控制台发布 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b78b1981-b227-4cf5-9435-6fc57963552a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5423c228b4ea9b8cd16bdac35a0e72c2fecbc232
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65301859"
---
# <a name="publishing-from-the-biztalk-server-administration-console"></a><span data-ttu-id="5ca22-102">从 BizTalk Server 管理控制台发布</span><span class="sxs-lookup"><span data-stu-id="5ca22-102">Publishing from the BizTalk Server Administration Console</span></span>
<span data-ttu-id="5ca22-103">如果你想要管理通过 BizTalk Server 管理控制台，而不是 ESB 管理门户发布的终结点，就可以做到在终结点的说明字段中输入一个通用描述、 发现和集成 (UDDI) 的名字对象若要将发布到 UDDI。</span><span class="sxs-lookup"><span data-stu-id="5ca22-103">If you want to manage endpoint publishing through the BizTalk Server Administration Console instead of the ESB Management Portal, you can do so by entering a Universal Description, Discovery, and Integration (UDDI) moniker in the description field of the endpoints to publish to UDDI.</span></span> <span data-ttu-id="5ca22-104">下面是示例名字对象。</span><span class="sxs-lookup"><span data-stu-id="5ca22-104">The following is an example moniker.</span></span>  
  
```  
uddi://TransportType=other;Status=Published.  
```  
  
 <span data-ttu-id="5ca22-105">可以设置以下 UDDI 属性使用**说明**字段在 BizTalk Server 管理控制台：</span><span class="sxs-lookup"><span data-stu-id="5ca22-105">You can set the following UDDI properties using the **Description** field in the BizTalk Server Administration Console:</span></span>  
  
-   <span data-ttu-id="5ca22-106">**ModifiedBy**。</span><span class="sxs-lookup"><span data-stu-id="5ca22-106">**ModifiedBy**.</span></span> <span data-ttu-id="5ca22-107">此可选属性包含修改终结点; 的用户的帐户名称例如，MyDomainName\MyUserName。</span><span class="sxs-lookup"><span data-stu-id="5ca22-107">This optional property contains the account name of the user that modified the endpoint; for example, MyDomainName\MyUserName.</span></span>  
  
-   <span data-ttu-id="5ca22-108">**UDDIContact**。</span><span class="sxs-lookup"><span data-stu-id="5ca22-108">**UDDIContact**.</span></span> <span data-ttu-id="5ca22-109">此可选属性是用户的为 UDDI 业务提供程序定义的联系人的名称。</span><span class="sxs-lookup"><span data-stu-id="5ca22-109">This optional property is the contact name of the user defined for the UDDI Business Provider.</span></span>  
  
-   <span data-ttu-id="5ca22-110">**UDDIUserType**。</span><span class="sxs-lookup"><span data-stu-id="5ca22-110">**UDDIUserType**.</span></span> <span data-ttu-id="5ca22-111">此可选属性是用户定义的 UDDI 业务提供程序的用户类型。</span><span class="sxs-lookup"><span data-stu-id="5ca22-111">This optional property is the user type of the user defined for the UDDI Business Provider.</span></span>  
  
-   <span data-ttu-id="5ca22-112">**UDDIEmail**。</span><span class="sxs-lookup"><span data-stu-id="5ca22-112">**UDDIEmail**.</span></span> <span data-ttu-id="5ca22-113">此可选属性是用户的 UDDI 业务提供程序定义的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="5ca22-113">This optional property is the e-mail address of the user defined for the UDDI Business Provider.</span></span>  
  
-   <span data-ttu-id="5ca22-114">**TransportType**。</span><span class="sxs-lookup"><span data-stu-id="5ca22-114">**TransportType**.</span></span> <span data-ttu-id="5ca22-115">此可选属性是终结点适配器类型，例如**文件中，MQS、 Wcf-wshttp、 SOAP、 HTTP**或**FTP**。</span><span class="sxs-lookup"><span data-stu-id="5ca22-115">This optional property is the endpoint adapter type, such as **FILE, MQS, WCF-WsHttp, SOAP, HTTP,** or **FTP**.</span></span>  
  
-   <span data-ttu-id="5ca22-116">**状态**。</span><span class="sxs-lookup"><span data-stu-id="5ca22-116">**Status**.</span></span> <span data-ttu-id="5ca22-117">此可选属性的状态是终结点，如**已发布**或**挂起**。</span><span class="sxs-lookup"><span data-stu-id="5ca22-117">This optional property is the status of the endpoint, such as **Published** or **Pending**.</span></span> <span data-ttu-id="5ca22-118">UDDI 发布服务使用此属性来发现终结点的状态。</span><span class="sxs-lookup"><span data-stu-id="5ca22-118">The UDDI Publishing Service uses this attribute to discover the status of the endpoint.</span></span>  
  
-   <span data-ttu-id="5ca22-119">**BindingType**。</span><span class="sxs-lookup"><span data-stu-id="5ca22-119">**BindingType**.</span></span> <span data-ttu-id="5ca22-120">此可选属性是特定协议 （URL 类型），UDDI 绑定支持，如**mailto，http、 https、 ftp、 传真、 电话**或**其他**。</span><span class="sxs-lookup"><span data-stu-id="5ca22-120">This optional property is the specific protocol (URL Type) that the UDDI binding supports, such as **mailto, http, https, ftp, fax, phone,** or **other**.</span></span> <span data-ttu-id="5ca22-121">UDDI 发布服务使用此属性来创建终结点绑定。</span><span class="sxs-lookup"><span data-stu-id="5ca22-121">The UDDI Publishing Service uses this attribute to create the endpoint binding.</span></span>