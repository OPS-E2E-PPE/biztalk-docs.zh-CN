---
title: 第 2 步：在服务器上配置 NLB |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Network Load Balancing
- configuring, NLB
- NLB
ms.assetid: 30b2f645-b495-49a5-852b-cf89d25fd2b7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad409c9a4287cee985d0a7f270370b97d5d8cf4b
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530015"
---
# <a name="step-2-configuring-nlb-on-the-servers"></a>第 2 步：在服务器上配置 NLB
安装基础平台并使用适当的网络设置配置服务器后 (请参阅[步骤 1:安装基础平台](../../adapters-and-accelerators/accelerator-swift/step-1-installing-the-base-platform.md))，可能需要启用 BizTalk HTTP 前端服务器和 BizTalk 消息传送服务器的负载均衡。 仅当你有一个或多个 BizTalk HTTP 前端服务器从一个或多个 BizTalk 消息传送服务器的单独计算机上安装，则需要此步骤。  
  
 负载均衡可确保客户端计算机 （Internet Explorer 用户浏览到 MRSR 站点） 和 MRSR 服务器之间以及 MRSR 服务器和邮件服务器之间的高可用性通信。  
  
 上进行负载均衡**公共**启用 Intranet 用户连接到这些计算机上的 IIS Web 服务器所需的接口在 HTTP 前端服务器。 上进行负载均衡**专用**启用邮件的服务器联系这些计算机上的 web 服务所需的接口在 HTTP 前端服务器。  
  
 消息传送在服务器上，假设有两个服务器配置上的负载平衡**专用**网络适配器。  
  
 有关详细信息，请参阅 BizTalk Server 部署指南。