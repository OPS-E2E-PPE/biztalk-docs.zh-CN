---
title: 是否有哪个版本的 BizTalk Server？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb651202-f682-4e5f-8a79-221877af20a7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 974999da3d74075fa218e078d1a757a83dbd325e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395151"
---
# <a name="what-version-of-biztalk-server-do-i-have"></a>是否有哪个版本的 BizTalk Server？
您可能会运行不同版本和不同版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 本主题演示如何确定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装信息，包括版本数、 版本和安装路径。  

## <a name="use-the-registry"></a>使用注册表

1. 选择**启动**，类型`regedt32`，然后打开它。  

2. 展开**HKEY_LOCAL_MACHINE**，展开**软件**，展开**Microsoft**，展开**BizTalk Server**，然后选择**3.0**。  

3. 右窗格中显示安装的信息，包括：  


   |      子键       |                                                                                                         Description                                                                                                          |
   |--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  **InstallPath**   |                                             列出安装的安装路径[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。                                              |
   | **ProductEdition** |                                                        列出版本，包括：<br /><br /> -开发人员<br />分支<br />-   Standard<br />-企业                                                         |
   | ProductVersion | 列出基本产品版本。 有关特定产品版本，包括 service pack 和累积更新，请参阅[的 BizTalk 版本](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx)。 |

## <a name="use-the-control-panel"></a>使用控制面板

1.  选择**启动**，类型`Programs and Features`，然后打开它。  

2. 在列表中，选择**Microsoft BizTalk Server**。 列出的版本和版本。

请参阅[的 BizTalk 版本](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx)。

## <a name="see-also"></a>请参阅  
 [入门](../core/getting-started-with-biztalk-server.md)