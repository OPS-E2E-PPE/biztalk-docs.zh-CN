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
ms.openlocfilehash: 60eee7ce4acb940d2d0011ead80bdcf9c5ed335c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254882"
---
# <a name="restrictions-on-the-smtp-host-property"></a><span data-ttu-id="723ad-102">对 SMTP 主机属性的限制</span><span class="sxs-lookup"><span data-stu-id="723ad-102">Restrictions on the SMTP Host Property</span></span>
<span data-ttu-id="723ad-103">SMTP 主机属性是一个字符串，指定将使用 SMTP 适配器将消息从 BizTalk server 发送的 SMTP 服务器。</span><span class="sxs-lookup"><span data-stu-id="723ad-103">The SMTP host property is a string that specifies the SMTP server that the SMTP adapter will use to send messages from the BizTalk server.</span></span>  
  
 <span data-ttu-id="723ad-104">为此属性适用以下规则和限制：</span><span class="sxs-lookup"><span data-stu-id="723ad-104">The following rules and restrictions apply to this property:</span></span>  
  
- <span data-ttu-id="723ad-105">必须在适配器处理程序级别中，在终结点级别或这两个位置中配置此属性。</span><span class="sxs-lookup"><span data-stu-id="723ad-105">This property must be configured on the adapter handler level, on the endpoint level, or in both places.</span></span>  
  
- <span data-ttu-id="723ad-106">SMTP 服务器属性不能包含以下字符: ' ~ ！</span><span class="sxs-lookup"><span data-stu-id="723ad-106">The SMTP server property cannot contain the following characters: \` ~ !</span></span> <span data-ttu-id="723ad-107">@ # $ ^ & \* ( ) = + [ ] { } \ &#124; ; : ' " , \< \> /, ?;</span><span class="sxs-lookup"><span data-stu-id="723ad-107">@ # $ ^ & \* ( ) = + [ ] { } \ &#124; ; : ' " , \< \> /, ?;</span></span>  
  
- <span data-ttu-id="723ad-108">SMTP 服务器名称的长度不得超过 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="723ad-108">The length of the SMTP server name must not exceed 256 characters.</span></span>  
  
  <span data-ttu-id="723ad-109">SMTP 适配器始终验证 SMTP 主机名称在设计时通过使用前面所述的规则。</span><span class="sxs-lookup"><span data-stu-id="723ad-109">The SMTP adapter always validates the SMTP host name at design time by using the previously mentioned rules.</span></span> <span data-ttu-id="723ad-110">此外，SMTP 适配器验证 SMTP 主机名称在运行时如果通过 SMTP 适配器的动态端口发送一条消息。</span><span class="sxs-lookup"><span data-stu-id="723ad-110">In addition, the SMTP adapter validates the SMTP host name at run time if a message is sent through a dynamic port with the SMTP adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="723ad-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="723ad-111">See Also</span></span>  
 [<span data-ttu-id="723ad-112">配置 SMTP 适配器时的限制</span><span class="sxs-lookup"><span data-stu-id="723ad-112">Restrictions When Configuring the SMTP Adapter</span></span>](../core/restrictions-when-configuring-the-smtp-adapter.md)