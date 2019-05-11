---
title: 如何远程用户登录到本地应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 886ee7cb-e6ba-476a-bea9-4bb4c22bf94e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fa3e3251961cb4d58d07026948a09fee94c2942
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336810"
---
# <a name="how-to-log-a-remote-user-on-to-a-local-application"></a><span data-ttu-id="5117f-102">如何远程用户登录到本地应用程序</span><span class="sxs-lookup"><span data-stu-id="5117f-102">How to Log a Remote User on to a Local Application</span></span>
<span data-ttu-id="5117f-103">企业单一登录服务 (ENTSSO) 的其他主要功能支持主机启动的进程 (HIP)。</span><span class="sxs-lookup"><span data-stu-id="5117f-103">The other main feature of Enterprise Single Sign-On service (ENTSSO) is supporting a host-initiated process (HIP).</span></span> <span data-ttu-id="5117f-104">当远程用户尝试访问本地 Windows 资源时，与 HIP 进行交互 ENTSSO。</span><span class="sxs-lookup"><span data-stu-id="5117f-104">ENTSSO interacts with HIP when a remote user tries to access a local Windows resource.</span></span> <span data-ttu-id="5117f-105">使用 ENTSSO，可以接收从主机用户并请求访问权限的请求到本地 Windows 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5117f-105">Using ENTSSO, you can receive the request from the host user and request access to the local Windows application.</span></span>  
  
## <a name="log-a-remote-user-on-to-a-local-windows-application"></a><span data-ttu-id="5117f-106">远程用户登录到本地的 Windows 应用程序</span><span class="sxs-lookup"><span data-stu-id="5117f-106">Log a remote user on to a local Windows application</span></span>  
  
1.  <span data-ttu-id="5117f-107">接收来自远程用户的请求。</span><span class="sxs-lookup"><span data-stu-id="5117f-107">Receive the request from the remote user.</span></span>  
  
     <span data-ttu-id="5117f-108">它由你负责确定如何检索来自远程用户的请求。</span><span class="sxs-lookup"><span data-stu-id="5117f-108">It is your responsibility to determine how to retrieve a request from the remote user.</span></span>  
  
2.  <span data-ttu-id="5117f-109">请求远程用户授予对指定的关联应用程序的访问权限使用`ISSOLookup2.LogonExternalUser`。</span><span class="sxs-lookup"><span data-stu-id="5117f-109">Request that the remote user be given access to the specified affiliate application, using `ISSOLookup2.LogonExternalUser`.</span></span>  
  
     <span data-ttu-id="5117f-110">`LogonExternalUser` 传入应用程序的外部用户希望访问，外部用户，以及所有相关标志的外部用户，关联的凭据的名称。</span><span class="sxs-lookup"><span data-stu-id="5117f-110">`LogonExternalUser` passes in the name of the application the external user wishes to access, the name of the external user, the associated credentials for the external user, and any relevant flags.</span></span> <span data-ttu-id="5117f-111">如果成功，`LogonExternalUser`向 Windows 访问标记返回一个句柄。</span><span class="sxs-lookup"><span data-stu-id="5117f-111">If successful, `LogonExternalUser` returns a handle to a Windows access token.</span></span>  
  
     <span data-ttu-id="5117f-112">必须已为远程用户实现单一登录数据库中，已在数据库中，将其凭据以及与关联应用程序相关联。</span><span class="sxs-lookup"><span data-stu-id="5117f-112">The remote user must already be identified in the Single Sign-On database, have their credentials in the database, and be associated with an affiliate application.</span></span> <span data-ttu-id="5117f-113">否则为`LogonExternalUser`返回错误。</span><span class="sxs-lookup"><span data-stu-id="5117f-113">Otherwise, `LogonExternalUser` returns an error.</span></span> <span data-ttu-id="5117f-114">可以保留的用户名称和最新使用密码同步的凭据。</span><span class="sxs-lookup"><span data-stu-id="5117f-114">You can keep the user names and credentials up to date using Password Sync.</span></span>  
  
     <span data-ttu-id="5117f-115">此外，您必须启用协议转换。</span><span class="sxs-lookup"><span data-stu-id="5117f-115">In addition, you must have protocol transition enabled.</span></span>  
  
3.  <span data-ttu-id="5117f-116">使用从返回的 Windows 句柄`LogonExternalUser`来模拟该标记代表的用户。</span><span class="sxs-lookup"><span data-stu-id="5117f-116">Use the Windows handle returned from `LogonExternalUser` to impersonate the user that the token represents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5117f-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="5117f-117">See Also</span></span>  
 <span data-ttu-id="5117f-118">[如何登录的本地用户身份登录到非 Windows 应用程序](../core/how-to-log-a-local-user-on-to-a-non-windows-application.md) </span><span class="sxs-lookup"><span data-stu-id="5117f-118">[How to Log a Local User on to a Non-Windows Application](../core/how-to-log-a-local-user-on-to-a-non-windows-application.md) </span></span>  
 <span data-ttu-id="5117f-119">**ISSOLookup2.LogonExternalUser 方法** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="5117f-119">**ISSOLookup2.LogonExternalUser Method** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>