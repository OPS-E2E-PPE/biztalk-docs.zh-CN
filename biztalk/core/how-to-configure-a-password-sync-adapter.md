---
title: 如何配置密码同步适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0effdc9b-4aee-4674-90c5-03dfd7cc4cd6
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f0be0146e905ef291942bd30adc111eff89e989
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247349"
---
# <a name="how-to-configure-a-password-sync-adapter"></a><span data-ttu-id="0dd79-102">如何配置密码同步适配器</span><span class="sxs-lookup"><span data-stu-id="0dd79-102">How to Configure a Password Sync Adapter</span></span>
<span data-ttu-id="0dd79-103">创建完密码同步适配器之后，必须将该适配器加载到系统中。</span><span class="sxs-lookup"><span data-stu-id="0dd79-103">After you have finished creating your password sync adapter, you must load your adapter on to a system.</span></span> <span data-ttu-id="0dd79-104">此外，还必须通知企业单一登录 (ENTSSO) 和配置存储，您的应用程序是一个密码同步适配器。</span><span class="sxs-lookup"><span data-stu-id="0dd79-104">Additionally, you must inform Enterprise Single Sign-On (ENTSSO) and the configuration store that your application is a password sync adapter.</span></span> <span data-ttu-id="0dd79-105">必须将注册配置存储区出于安全目的： 你的适配器将请求更新密码和其他凭据。</span><span class="sxs-lookup"><span data-stu-id="0dd79-105">You must register with the configuration store for security purposes: your adapter will request updates to passwords and other credentials.</span></span> <span data-ttu-id="0dd79-106">因此，ENTSSO 必须知道允许给定的适配器请求此类权限。</span><span class="sxs-lookup"><span data-stu-id="0dd79-106">Therefore, ENTSSO must know that a given adapter is allowed to ask for such permissions.</span></span>  
  
### <a name="to-configure-a-password-sync-adapter"></a><span data-ttu-id="0dd79-107">配置密码同步适配器</span><span class="sxs-lookup"><span data-stu-id="0dd79-107">To configure a password sync adapter</span></span>  
  
1.  <span data-ttu-id="0dd79-108">使用 ssops 工具创建具有配置存储的适配器。</span><span class="sxs-lookup"><span data-stu-id="0dd79-108">Create your adapter with the configuration store using the ssops tool.</span></span>  
  
     <span data-ttu-id="0dd79-109">使用 ssops 将 XML 配置文件加载到配置数据库中，以便向企业单一登录描述您的应用程序。</span><span class="sxs-lookup"><span data-stu-id="0dd79-109">Using ssops, you load an XML configuration file into the configuration database that describes your application to Enterprise Single Sign-On.</span></span>  
  
2.  <span data-ttu-id="0dd79-110">与配置数据库创建适配器之后，你可以修改的适配器信息`ISSOPSAdmin.SetAdapterProperties`。</span><span class="sxs-lookup"><span data-stu-id="0dd79-110">After you create the adapter with the config database, you can modify the adapter information with `ISSOPSAdmin.SetAdapterProperties`.</span></span>  
  
     <span data-ttu-id="0dd79-111">尽管两种方法非常相似，`SetAdapterProperties`配置信息更改时，将消息发送到适配器。</span><span class="sxs-lookup"><span data-stu-id="0dd79-111">While the two methods are similar, `SetAdapterProperties` sends a message to the adapter when the configuration information changes.</span></span>  
  
3.  <span data-ttu-id="0dd79-112">若要删除适配器，请使用 ISSOAdmin.DeleteApplication。</span><span class="sxs-lookup"><span data-stu-id="0dd79-112">To delete an adapter, use ISSOAdmin.DeleteApplication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dd79-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0dd79-113">See Also</span></span>  
 [<span data-ttu-id="0dd79-114">同步密码</span><span class="sxs-lookup"><span data-stu-id="0dd79-114">Synchronizing Passwords</span></span>](../core/synchronizing-passwords.md)