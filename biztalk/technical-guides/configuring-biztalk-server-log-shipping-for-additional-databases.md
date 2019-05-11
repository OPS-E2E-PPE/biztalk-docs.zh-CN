---
title: 配置 BizTalk 日志传送的其他数据库 |Microsoft Docs
description: 将自定义数据库添加到备份 BizTalk Server 作业和 BizTalk Server 中的日志传送
ms.custom: ''
ms.date: 11/01/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fc2ae67-5cb9-4d53-9bf7-c88f84914960
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b44031464846dbaab484a9eb29e672371778ddae
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244070"
---
# <a name="configuring-biztalk-server-log-shipping-for-additional-databases"></a>配置 BizTalk Server 日志传送的其他数据库

## <a name="overview"></a>概述
在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，添加到备份 BizTalk Server 作业的作业会自动添加到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送。 不需要采取其他步骤来配置新的数据库添加到备份 BizTalk Server 作业的日志传送。 但是，请确保将自定义数据库添加为在相应\<OtherDatabases\> SampleUpdateInfo.xml 文件部分。 [为使日志传送配置的目标系统](../core/how-to-configure-the-destination-system-for-log-shipping.md)并[返回自定义数据库](../core/how-to-back-up-custom-databases.md)提供一些指导。
  
## <a name="see-also"></a>请参阅  
 [配置 BizTalk Server 日志传送](../technical-guides/configuring-biztalk-server-log-shipping.md)