---
title: 密码同步编程体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 679edbf1-fb08-4472-b366-3e1d361b20e7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9da005574ef041eaa20582d02d1affd196963c81
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394992"
---
# <a name="password-sync-programming-architecture"></a><span data-ttu-id="9308b-102">密码同步编程体系结构</span><span class="sxs-lookup"><span data-stu-id="9308b-102">Password Sync Programming Architecture</span></span>
<span data-ttu-id="9308b-103">密码同步适配器使用拉模型与企业单一登录系统的其余部分进行交互： 即，该适配器主动接收密码更改从企业单一登录 (ENTSSO) 服务以及非 Windows 系统中。</span><span class="sxs-lookup"><span data-stu-id="9308b-103">A password sync adapter uses a pull model for interacting with the rest of the Enterprise Single Sign-On system: that is, the adapter actively receives password changes from the Enterprise Single Sign-On (ENTSSO) service and also from the non-Windows system.</span></span> <span data-ttu-id="9308b-104">同样，适配器将推送到另一个系统收到的密码更改。</span><span class="sxs-lookup"><span data-stu-id="9308b-104">Similarly, the adapter pushes password changes received from one system to the other.</span></span> <span data-ttu-id="9308b-105">与此模型中，您的适配器具有三个体系结构组件进行交互： ENTSSO 体系结构、 密码同步 (PS) 助手组件和指定的非 Windows 系统。</span><span class="sxs-lookup"><span data-stu-id="9308b-105">With this model, your adapter interacts with three architectural components: the ENTSSO architecture, the Password Sync (PS) Helper component, and a specified non-Windows system.</span></span>  
  
## <a name="enterprise-single-sign-on-architecture"></a><span data-ttu-id="9308b-106">企业单一登录体系结构</span><span class="sxs-lookup"><span data-stu-id="9308b-106">Enterprise Single Sign-On Architecture</span></span>  
 <span data-ttu-id="9308b-107">ENTSSO 是实现企业单一登录技术，并作为本地服务运行于适配器所在的同一系统上的服务。</span><span class="sxs-lookup"><span data-stu-id="9308b-107">ENTSSO is the service that implements the Enterprise Single Sign-On technology, and runs as a local service on the same system as your adapter.</span></span> <span data-ttu-id="9308b-108">因此，适配器与 ENTSSO 之间的通信始终是本地的。</span><span class="sxs-lookup"><span data-stu-id="9308b-108">Therefore, communication between the adapter and ENTSSO is always local.</span></span> <span data-ttu-id="9308b-109">但是，密码同步适配器从 ENTSSO 服务的单独进程中运行。</span><span class="sxs-lookup"><span data-stu-id="9308b-109">However, a password sync adapter runs in a separate process from the ENTSSO service.</span></span>  
  
 <span data-ttu-id="9308b-110">ENTSSO 使用配置存储来存储适配器的配置信息。</span><span class="sxs-lookup"><span data-stu-id="9308b-110">ENTSSO uses the configuration store to store configuration information for an adapter.</span></span> <span data-ttu-id="9308b-111">配置存储应用程序的应用程序用户帐户与访问帐户相对应。</span><span class="sxs-lookup"><span data-stu-id="9308b-111">The Application Users account of a configuration store application corresponds to the access account.</span></span> <span data-ttu-id="9308b-112">当适配器调用 entsso 时，ENTSSO 将检查适配器为该适配器已配置的访问帐户中。</span><span class="sxs-lookup"><span data-stu-id="9308b-112">When an adapter calls into ENTSSO, ENTSSO checks that the adapter is within the configured access account for that adapter.</span></span> <span data-ttu-id="9308b-113">访问帐户必须是组的帐户 （本地或域） 帐户。</span><span class="sxs-lookup"><span data-stu-id="9308b-113">The access account must be a (local or domain) group account.</span></span>  
  
 <span data-ttu-id="9308b-114">由于 ENTSSO 存储有关适配器的信息，该适配器可以向 ENTSSO 标识自身通过自己的名称。</span><span class="sxs-lookup"><span data-stu-id="9308b-114">Because ENTSSO stores information about an adapter, the adapter can identify itself to ENTSSO by its adapter name.</span></span> <span data-ttu-id="9308b-115">适配器名称对应于配置存储应用程序名称和配置存储标识符，用于存储适配器属性。</span><span class="sxs-lookup"><span data-stu-id="9308b-115">The adapter name corresponds to the configuration store application name and the configuration store identifier used to store the adapter properties.</span></span> <span data-ttu-id="9308b-116">因此，适配器必须知道只有自己的适配器名称以访问配置信息和正确地标识自身向 ENTSSO 系统在运行时。</span><span class="sxs-lookup"><span data-stu-id="9308b-116">Therefore, adapters must know only their adapter name to access configuration information and to correctly identify themselves to the ENTSSO system at run time.</span></span>  
  
## <a name="password-sync-helper"></a><span data-ttu-id="9308b-117">密码同步助手</span><span class="sxs-lookup"><span data-stu-id="9308b-117">Password Sync Helper</span></span>  
 <span data-ttu-id="9308b-118">密码同步 (PS) 助手是 ENTSSO 提供的一个 COM 组件。</span><span class="sxs-lookup"><span data-stu-id="9308b-118">Password Sync (PS) Helper is a COM component provided by ENTSSO.</span></span> <span data-ttu-id="9308b-119">PS 帮助程序以进程形式运行与密码同步适配器，并公开 ISSOPSWrapper。</span><span class="sxs-lookup"><span data-stu-id="9308b-119">PS Helper runs in-process with the password sync adapter, and exposes ISSOPSWrapper.</span></span> <span data-ttu-id="9308b-120">该适配器可以调用任一接口与 ENTSSO 服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="9308b-120">Your adapter can call either interface to communicate with the ENTSSO service.</span></span> <span data-ttu-id="9308b-121">PS 助手传递通信与 entsso 之间使用加密 （数据包保密性） 轻量远程过程调用 (LRPC)。</span><span class="sxs-lookup"><span data-stu-id="9308b-121">The PS Helper passes communications to and from ENTSSO using encrypted (packet privacy) lightweight remote procedure call (LRPC).</span></span> <span data-ttu-id="9308b-122">尽管通信主要用于密码更新，但您可以使用接口的适配器和 ENTSSO 之间传递其他类型的通知。</span><span class="sxs-lookup"><span data-stu-id="9308b-122">Although the communications are mainly for password updates, you can also use the interfaces to pass other types of notifications between the adapter and ENTSSO.</span></span> <span data-ttu-id="9308b-123">由于 PS 助手在每个进程的单一实例值作为运行，就可以为多个适配器来调用同一 PS 助手对象从同一适配器进程内。</span><span class="sxs-lookup"><span data-stu-id="9308b-123">Because PS Helper runs as a singleton value per process, it is possible for multiple adapters to call the same PS Helper object from within the same adapter process.</span></span> <span data-ttu-id="9308b-124">有关以编程方式使用 PS 助手的详细信息，请参阅[同步密码](../core/synchronizing-passwords.md)。</span><span class="sxs-lookup"><span data-stu-id="9308b-124">For more information about using PS Helper programmatically, see [Synchronizing Passwords](../core/synchronizing-passwords.md).</span></span>  
  
## <a name="non-windows-system"></a><span data-ttu-id="9308b-125">非 Windows 系统</span><span class="sxs-lookup"><span data-stu-id="9308b-125">Non-Windows System</span></span>  
 <span data-ttu-id="9308b-126">非 Windows 系统是与您的适配器进行交互的远程计算机。</span><span class="sxs-lookup"><span data-stu-id="9308b-126">The non-Windows system is the remote computer your adapter interacts with.</span></span> <span data-ttu-id="9308b-127">如何与非 Windows 系统进行交互是取决于您。</span><span class="sxs-lookup"><span data-stu-id="9308b-127">How you interact with the non-Windows system is up to you.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9308b-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="9308b-128">See Also</span></span>  
 [<span data-ttu-id="9308b-129">密码同步适配器</span><span class="sxs-lookup"><span data-stu-id="9308b-129">Password Sync Adapters</span></span>](../core/password-sync-adapters.md)