---
title: 安装证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, installing
- installing, certificates
ms.assetid: 7525f771-623c-420f-99ca-c834e819829d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d1593c28186e0b5f96c749e67469257592e291d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377287"
---
# <a name="installing-certificates"></a><span data-ttu-id="f7b09-102">安装证书</span><span class="sxs-lookup"><span data-stu-id="f7b09-102">Installing Certificates</span></span>
<span data-ttu-id="f7b09-103">若要发送、 修复或将消息提交，您必须安装了正确的证书。</span><span class="sxs-lookup"><span data-stu-id="f7b09-103">To send, repair, or submit messages, you must have the proper certificates installed.</span></span> <span data-ttu-id="f7b09-104">本主题介绍如何添加证书。</span><span class="sxs-lookup"><span data-stu-id="f7b09-104">This topic describes how to add certificates.</span></span> <span data-ttu-id="f7b09-105">在生产环境中，请参阅 IT 部门以获得证书。</span><span class="sxs-lookup"><span data-stu-id="f7b09-105">In a production environment, see your IT department for certificates.</span></span>  

 <span data-ttu-id="f7b09-106">**摘要**</span><span class="sxs-lookup"><span data-stu-id="f7b09-106">**Summary**</span></span>  

 <span data-ttu-id="f7b09-107">本部分说明如何创建并存储在以下证书：</span><span class="sxs-lookup"><span data-stu-id="f7b09-107">This section provides instructions on how to create and store the following certificates:</span></span>  

- <span data-ttu-id="f7b09-108">每个客户端计算机上的每个消息修复和新提交证书-当前用户的个人文件夹中的角色的证书存储</span><span class="sxs-lookup"><span data-stu-id="f7b09-108">Certificates for each of the Message Repair and New Submission roles in the Personal folder of the Certificates - Current User store on each client computer</span></span>  

- <span data-ttu-id="f7b09-109">每个 BizTalk 业务流程服务器计算机上的每个消息修复和新提交的证书 （本地计算机） 的其他人文件夹中的角色的证书存储</span><span class="sxs-lookup"><span data-stu-id="f7b09-109">Certificates for each of the Message Repair and New Submission roles in the Other People folder of the Certificates (Local Computer) store on each BizTalk orchestration server computer</span></span>  

- <span data-ttu-id="f7b09-110">为每个客户端计算机上的证书 （本地计算机） 存储中的受信任的根证书颁发机构文件夹的证书颁发机构的证书</span><span class="sxs-lookup"><span data-stu-id="f7b09-110">Certification Authority's certificate into the Trusted Root Certification Authorities folder in the Certificates (Local Computer) store on each client computer</span></span>  

  <span data-ttu-id="f7b09-111">如果您部署了[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]一台计算机上，而且还必须安装在同一台计算机上的证书服务器，需要为 Microsoft SharePoint Server 从管理路径排除证书服务器。</span><span class="sxs-lookup"><span data-stu-id="f7b09-111">If you have deployed [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] on a single computer, and also have a certificate server installed on the same computer, you need to exclude the certificate server from the managed paths for Microsoft SharePoint Server.</span></span>  

  <span data-ttu-id="f7b09-112">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="f7b09-112">This section contains:</span></span>  

- [<span data-ttu-id="f7b09-113">将证书添加到客户端上的证书存储</span><span class="sxs-lookup"><span data-stu-id="f7b09-113">Adding Certificates to the Certificates Store on the Client</span></span>](../../adapters-and-accelerators/accelerator-swift/adding-certificates-to-the-certificates-store-on-the-client.md)  

- [<span data-ttu-id="f7b09-114">将证书添加到服务器上的证书存储</span><span class="sxs-lookup"><span data-stu-id="f7b09-114">Adding Certificates to the Certificates Store on the Server</span></span>](../../adapters-and-accelerators/accelerator-swift/adding-certificates-to-the-certificates-store-on-the-server.md)  

- [<span data-ttu-id="f7b09-115">从单台计算机部署的管理路径中排除证书服务器</span><span class="sxs-lookup"><span data-stu-id="f7b09-115">Excluding CertSrv from Managed Paths on a Single-Computer Deployment</span></span>](../../adapters-and-accelerators/accelerator-swift/excluding-certsrv-from-managed-paths-on-a-single-computer-deployment.md)
