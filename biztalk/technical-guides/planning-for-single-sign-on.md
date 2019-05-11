---
title: 规划单一登录 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d1bc220-4087-4603-ac15-6bb0c62c59d4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4677eca7a6314da15f86257e17dbaf33cf0b8224
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400696"
---
# <a name="planning-for-single-sign-on"></a>规划单一登录
企业单一登录 (SSO) 是一个关键组成部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行的时将不能没有 SSO 服务，因为所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器配置信息加密，并在 SSO 数据库中存储和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]访问此信息通过 SSO 服务。 如果 SSO 服务未在 BizTalk server 上运行，或如果 SSO 服务不具有对 SSO 主密钥服务器的访问，此适配器配置信息不可访问。  
  
 SSO 实施应包括以下计划。  
  
## <a name="backing-up-the-master-secret"></a>备份主密钥  
 如果 SSO 主密钥服务器失败，并且丢失了密钥，或者密钥损坏，您将不能检索存储在 SSO 数据库中的数据。 您必须备份主密钥或风险会丢失 SSO 数据库中的数据。 因此，它是 SSO 主密钥进行备份和存储在安全位置非常重要。 有关 SSO 主密钥备份的信息，请参阅[如何返回主密钥](http://go.microsoft.com/fwlink/?LinkId=151395)(http://go.microsoft.com/fwlink/?LinkId=151395)。  
  
## <a name="configuring-sso-for-high-availability"></a>配置高可用性的 SSO  
 由于 SSO 是此类的关键组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中，应以实现高可用性配置 SSO 主密钥服务器。 如有可能，应按照中的步骤群集企业单一登录主密钥服务器上的服务[聚类分析主密钥服务器](../technical-guides/clustering-the-master-secret-server.md)。 如果您不有权访问 Windows Server 群集，你仍可以提供高可用性的主密钥服务器上的企业单一登录服务按照主题中所述的步骤[指定新的主服务器密钥服务器手动](../technical-guides/designating-a-new-master-secret-server-manually.md)。  
  
## <a name="following-established-sso-security-recommendations"></a>以下建立的 SSO 安全建议  
 遵循本主题中所述的 SSO 安全建议[SSO 安全建议](http://go.microsoft.com/fwlink/?LinkId=155753)(http://go.microsoft.com/fwlink/?LinkId=155753)。