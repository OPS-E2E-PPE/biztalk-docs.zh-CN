---
title: 对 SMTP 主机属性的限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], restrictions
- SMTP adapters, restrictions
ms.assetid: 6dbdb6dc-0062-4444-a4c8-6e2a7900f533
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2e8ef3800b67119bf9ffaffb4fd069064b640d1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985342"
---
# <a name="restrictions-on-the-smtp-host-property"></a><span data-ttu-id="fd60e-102">对 SMTP 主机属性的限制</span><span class="sxs-lookup"><span data-stu-id="fd60e-102">Restrictions on the SMTP Host Property</span></span>
<span data-ttu-id="fd60e-103">SMTP 主机属性是一个字符串，它指定 SMTP 适配器将用于从 BizTalk 服务器发送消息的 SMTP 服务器。</span><span class="sxs-lookup"><span data-stu-id="fd60e-103">The SMTP host property is a string that specifies the SMTP server that the SMTP adapter will use to send messages from the BizTalk server.</span></span>  
  
 <span data-ttu-id="fd60e-104">此属性适用以下规则和限制：</span><span class="sxs-lookup"><span data-stu-id="fd60e-104">The following rules and restrictions apply to this property:</span></span>  
  
- <span data-ttu-id="fd60e-105">必须在适配器处理程序级别、终结点级别或同时在这两个级别上配置此属性。</span><span class="sxs-lookup"><span data-stu-id="fd60e-105">This property must be configured on the adapter handler level, on the endpoint level, or in both places.</span></span>  
  
- <span data-ttu-id="fd60e-106">SMTP 服务器属性不能包含以下字符: ' ~ ！</span><span class="sxs-lookup"><span data-stu-id="fd60e-106">The SMTP server property cannot contain the following characters: \` ~ !</span></span> <span data-ttu-id="fd60e-107">@ # $ ^ & \* ( ) = + [ ] { } \ &#124; ; : ' " , \< \> /, ?;</span><span class="sxs-lookup"><span data-stu-id="fd60e-107">@ # $ ^ & \* ( ) = + [ ] { } \ &#124; ; : ' " , \< \> /, ?;</span></span>  
  
- <span data-ttu-id="fd60e-108">SMTP 服务器名称的长度不得超过 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="fd60e-108">The length of the SMTP server name must not exceed 256 characters.</span></span>  
  
  <span data-ttu-id="fd60e-109">SMTP 适配器将始终在设计时通过使用上述规则验证 SMTP 主机名称。</span><span class="sxs-lookup"><span data-stu-id="fd60e-109">The SMTP adapter always validates the SMTP host name at design time by using the previously mentioned rules.</span></span> <span data-ttu-id="fd60e-110">此外，如果 SMTP 适配器通过动态端口发送消息，则它将在运行时验证 SMTP 主机名称。</span><span class="sxs-lookup"><span data-stu-id="fd60e-110">In addition, the SMTP adapter validates the SMTP host name at run time if a message is sent through a dynamic port with the SMTP adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd60e-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd60e-111">See Also</span></span>  
 [<span data-ttu-id="fd60e-112">配置 SMTP 适配器时的限制</span><span class="sxs-lookup"><span data-stu-id="fd60e-112">Restrictions When Configuring the SMTP Adapter</span></span>](../core/restrictions-when-configuring-the-smtp-adapter.md)