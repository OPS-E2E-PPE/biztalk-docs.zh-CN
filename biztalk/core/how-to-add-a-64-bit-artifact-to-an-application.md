---
title: 如何将一个 64 位项目添加到应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- artifacts, 64-bit support
- scripts, 64-bit support
- virtual directories, 64-bit support
- artifacts, applications
- 64-bit support, COM components
- 64-bit support, virtual directories
- applications, artifacts
- 64-bit support, scripts
- 64-bit support, artifacts
- COM components, 64-bit support
- BizTalk Server, 64-bit support
- applications, 64-bit support
ms.assetid: 46aca7d4-c5be-421e-b16d-7f3095c8cc67
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 041b08e6039e49376c14a83ba61fa6dab3a2e1fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387448"
---
# <a name="how-to-add-a-64-bit-artifact-to-an-application"></a>如何将一个 64 位项目添加到应用程序
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 包括对 64 位应用程序的支持。 这意味着，您可以添加 64 位项目到 BizTalk 应用程序与 32 位项目; 相同的方式但是，在 32 位计算机上安装以下 64 位项目时可能会遇到以下问题：  
  
- **从 Web 服务器正在运行 64 位辅助进程的虚拟目录。** 虚拟目录将安装在 32 位计算机上，但它可能无法正常运行。 将记录不匹配。  
  
- **非托管的 COM 或托管 COM + 组件标记为 64 位。** 这些组件将不安装在 32 位计算机上。  
  
- **64 位脚本另存为.exe 文件。** 此类型的脚本可能无法正常工作。  
  
  添加项目的一般说明，请参阅[如何创建或添加项目](../core/how-to-create-or-add-an-artifact.md)。 有关添加特定项目类型的说明，请参阅[管理项目](../core/managing-artifacts.md)。  
  
## <a name="see-also"></a>请参阅  
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)   
 [如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)