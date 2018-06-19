---
title: 更新、 修复或卸载 BizTalk Accelerator for HL7 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2fc84d2-1262-4a6e-ae9c-488a00ab4099
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5b4fa1dba322e830114a76a0ca69134edbb1d06
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
ms.locfileid: "25962171"
---
# <a name="update-repair-or-uninstall-biztalk-accelerator-for-hl7"></a>更新、 修复或卸载 BizTalk Accelerator for HL7

更改、 修复或卸载[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]。  
  
> [!IMPORTANT]
>  请务必卸载[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]卸载之前[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]如果无法卸载[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]不再安装。  

## <a name="prerequisites"></a>必要條件
* 使用成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理员组。  

* 此用户帐户还必须是 Administrators 组的成员上[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]存储 BizTalk Accelerator for HL7 数据。  
    
## <a name="update-an-existing-installation"></a>更新现有安装

> [!NOTE]
>  当你修改你的安装[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]，端到端教程不会自动运行。 
> 
> 若要运行本教程并验证是否正确执行修改的安装，运行手动从教程***\<驱动器\>*** **files\microsoft BizTalk \<版本\>Accelerator for HL7\SDK\End 端到端教程**文件夹。
  
1. 运行[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] **setup.exe**以管理员身份 
  
2.  在欢迎页上，选择**下一步**。  
  
3.  在**程序维护**，选择**修改**，然后选择**下一步**。  
  
4.  在**自定义安装**，选择你想要安装的功能，清除功能您不想，，然后选择**下一步**。  
  
5.  在摘要中，选择**下一步**。  
  
6.  选择“安装”。  
  
7. 完成时，选择“完成”。  

## <a name="repair-an-existing-installation"></a>修复现有安装
[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]向导通过修正丢失或损坏的文件、 快捷方式或注册表项，修复安装。  
  
1. 运行[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] **setup.exe**以管理员身份。  
  
2.  在欢迎页上，选择**下一步**。  
  
3.  在**程序维护**，选择**修复**，然后选择**下一步**。  
  
4.  在**日志记录服务帐户**，重新输入用户帐户，然后选择**确定**。  
  
4.  如果系统提示**帐户名称已被授予登录，作为一种服务右**，然后选择**确定**以继续。  
  
5.  当准备好修复时，选择**安装**。  
  
6. 当完成后，选择**完成**。 

  
## <a name="uninstall-btahl7"></a>卸载 BTAHL7  

> [!IMPORTANT]
>  如果没有接收位置或发送端口使用 MLLP 传输类型，BTAHL7 安装程序不会在 BTAHL7 卸载过程删除 MLLP 适配器。 在卸载之前，请删除所有接收位置或发送端口使用 MLLP 传输。 或者，将从 MLLP 的传输类型更改为另一种类型。 然后，卸载将删除 MLLP 适配器。  
      
1.  打开“程序和功能”。  
  
2.  选择[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]，然后选择**卸载**。  
  
4.  选择**是**如果系统询问以确认。 
  
5.  当完成后，选择**完成**。  
  
    > [!NOTE]
    >  未自动卸载 BTAHL7[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目和程序集。  
  

  
## <a name="troubleshooting-installation-issues"></a>安装问题疑难解答  
 如果服务器将无法验证用户是否[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理员，卸载 BTAHL7 返回以下错误： 
 
 `Fatal error during uninstallation`  
  
若要继续卸载，请执行以下操作：  
  
1.  以本地管理员身份登录到服务器。  
  
2.  卸载 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
3.  卸载 [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]。  
  
## <a name="see-also"></a>另请参阅  
[安装或升级 Microsoft BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-or-upgrade-microsoft-biztalk-accelerator-for-hl7.md)