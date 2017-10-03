---
title: "如何登录到本地的应用程序的远程用户 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 886ee7cb-e6ba-476a-bea9-4bb4c22bf94e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f638007c3c4eb1f85a5b5a701dd2b456c2d220d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-log-a-remote-user-on-to-a-local-application"></a><span data-ttu-id="c6032-102">如何登录到本地的应用程序的远程用户</span><span class="sxs-lookup"><span data-stu-id="c6032-102">How to Log a Remote User on to a Local Application</span></span>
<span data-ttu-id="c6032-103">企业单一登录服务 (ENTSSO) 的另一主要功能是支持主机启动的进程 (HIP)。</span><span class="sxs-lookup"><span data-stu-id="c6032-103">The other main feature of Enterprise Single Sign-On service (ENTSSO) is supporting a host-initiated process (HIP).</span></span> <span data-ttu-id="c6032-104">当远程用户试图访问本地 Windows 资源时，ENTSSO 将与 HIP 进行交互。</span><span class="sxs-lookup"><span data-stu-id="c6032-104">ENTSSO interacts with HIP when a remote user tries to access a local Windows resource.</span></span> <span data-ttu-id="c6032-105">使用 ENTSSO，可以接收主机用户的请求，并请求对本地 Windows 应用程序进行访问。</span><span class="sxs-lookup"><span data-stu-id="c6032-105">Using ENTSSO, you can receive the request from the host user and request access to the local Windows application.</span></span>  
  
## <a name="log-a-remote-user-on-to-a-local-windows-application"></a><span data-ttu-id="c6032-106">登录到本地的 Windows 应用程序的远程用户</span><span class="sxs-lookup"><span data-stu-id="c6032-106">Log a remote user on to a local Windows application</span></span>  
  
1.  <span data-ttu-id="c6032-107">接收相应远程用户的请求。</span><span class="sxs-lookup"><span data-stu-id="c6032-107">Receive the request from the remote user.</span></span>  
  
     <span data-ttu-id="c6032-108">您需要确定如何检索来自相应远程用户的请求。</span><span class="sxs-lookup"><span data-stu-id="c6032-108">It is your responsibility to determine how to retrieve a request from the remote user.</span></span>  
  
2.  <span data-ttu-id="c6032-109">使用 `ISSOLookup2.LogonExternalUser` 请求授予远程用户对指定的关联应用程序的访问权限。</span><span class="sxs-lookup"><span data-stu-id="c6032-109">Request that the remote user be given access to the specified affiliate application, using `ISSOLookup2.LogonExternalUser`.</span></span>  
  
     <span data-ttu-id="c6032-110">`LogonExternalUser` 传入外部用户希望访问的应用程序的名称、该外部用户的名称、该用户的关联凭据以及所有相关标志。</span><span class="sxs-lookup"><span data-stu-id="c6032-110">`LogonExternalUser` passes in the name of the application the external user wishes to access, the name of the external user, the associated credentials for the external user, and any relevant flags.</span></span> <span data-ttu-id="c6032-111">如果成功，则 `LogonExternalUser` 会向 Windows 访问标记返回一个句柄。</span><span class="sxs-lookup"><span data-stu-id="c6032-111">If successful, `LogonExternalUser` returns a handle to a Windows access token.</span></span>  
  
     <span data-ttu-id="c6032-112">该远程用户必须已在单一登录数据库中标识，已将其凭据存储到该数据库中，并且已经与关联应用程序相关联。</span><span class="sxs-lookup"><span data-stu-id="c6032-112">The remote user must already be identified in the Single Sign-On database, have their credentials in the database, and be associated with an affiliate application.</span></span> <span data-ttu-id="c6032-113">否则，`LogonExternalUser` 将返回错误。</span><span class="sxs-lookup"><span data-stu-id="c6032-113">Otherwise, `LogonExternalUser` returns an error.</span></span> <span data-ttu-id="c6032-114">您可以利用密码同步使用户名和凭据保持最新状态。</span><span class="sxs-lookup"><span data-stu-id="c6032-114">You can keep the user names and credentials up to date using Password Sync.</span></span>  
  
     <span data-ttu-id="c6032-115">此外，您还必须启用协议转换。</span><span class="sxs-lookup"><span data-stu-id="c6032-115">In addition, you must have protocol transition enabled.</span></span>  
  
3.  <span data-ttu-id="c6032-116">使用从 `LogonExternalUser` 返回的 Windows 句柄来模拟该标记代表的用户。</span><span class="sxs-lookup"><span data-stu-id="c6032-116">Use the Windows handle returned from `LogonExternalUser` to impersonate the user that the token represents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6032-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6032-117">See Also</span></span>  
 <span data-ttu-id="c6032-118">[如何登录到非 Windows 应用程序的本地用户](../core/how-to-log-a-local-user-on-to-a-non-windows-application.md) </span><span class="sxs-lookup"><span data-stu-id="c6032-118">[How to Log a Local User on to a Non-Windows Application](../core/how-to-log-a-local-user-on-to-a-non-windows-application.md) </span></span>  
 <span data-ttu-id="c6032-119">**ISSOLookup2.LogonExternalUser 方法**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="c6032-119">**ISSOLookup2.LogonExternalUser Method** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>