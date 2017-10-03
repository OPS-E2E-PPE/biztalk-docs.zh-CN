---
title: "对队列管理的支持 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d60d06ba-8cf3-46d6-af59-626f12fc572a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faeb3f141e114cf1f86157084f50d0a0d490833a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="support-for-queue-management"></a>队列管理支持
与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MQSeries 适配器你现在可以创建和删除队列远程 MQSeries 队列管理器上。 这支持，因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用的远程 MQSAgent COM + 对象的通信直接与 MQSeries 队列管理器。 通常，在运行时使用此 MQSAgent 从远程 MQSeries 服务器队列读取信息和向其中写入消息。 此远程服务的客户端可以是多台 BizTalk 服务器。 此外，队列创建和删除功能由此 MQSAgent 提供，并可以从业务流程或适配器中直接调用。 这样可以实现高度动态的方案：业务流程或适配器创建一个临时队列，然后向其上发送消息，在另一个队列上接收回复，最后删除这个临时队列。  
  
## <a name="createqueue-and-deletequeue-apis"></a>CreateQueue 和 DeleteQueue API  
 CreateQueue 和 DeleteQueue API 定义如下。  
  
### <a name="structure-definition"></a>结构定义  
  
```  
typedef enum QueueUsage {  
      Normal       = 0,  
      Transmission = 1  
} QueueUsage;  
  
typedef enum ResultCode {  
      QueueAlreadyExists                     = 0, //  no bits set  
      QueueCreated                           = 1, //  QueueCreated  
      QueueCreatedAndRemoteDefinitionUpdated = 5, //  QueueCreated | RemoteDefinitionUpdated  
      QueueAndRemoteDefinitionCreated        = 7, //  QueueCreated | RemoteDefinitionCreated | RemoteDefinitionUpdated  
      QueueDoesNotExist                      = 8, //  QueueDoesNotExist  
      QueueDeleted                           = 16 //  QueueDeleted  
} ResultCode;  
```  
  
### <a name="interface-definition"></a>接口定义  
  
```  
[  
            object,  
            uuid(E90AC1A6-657B-4680-AF6A-89F11113FB8B),  
            dual,  
            nonextensible,  
            helpstring("IMQSAdmin Interface"),  
            pointer_default(unique)  
]  
interface IMQSAdmin2 : IDispatch{  
  
HRESULT CreateQueue (  
[in]BSTR queueManager,  
[in]BSTR newQueueName,  
[in]QueueUsage usage,  
[in]BSTR remoteDefinition,  
[in]BSTR remoteQName,  
[in]BSTR remoteQMgrName,  
[in]BOOL updateExistingRemoteDefinition,  
[out, retval]ResultCode* resultCode);  
  
HRESULT DeleteQueue (  
[in]BSTR queueManager,  
[in]BSTR newQueueName,  
[out, retval]ResultCode* resultCode);  
};  
  
      [  
            uuid(412AF00D-7CA8-4d2a-AFF6-F61CE2E29A0D),  
            helpstring("MQSAdmin Class")  
      ]  
      coclass MQSAdmin  
      {  
            [default] interface IMQSAdmin2;  
      };  
  
```  
  
## <a name="examples"></a>示例  
 完成示例 1 中的步骤可创建一个 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] C# 控制台应用程序，该程序可用于创建或删除 MQSeries Server 队列。  
  
### <a name="example-1"></a>示例 1  
  
##### <a name="create-a-c-console-application-to-manage-mqseries-server-queues"></a>创建一个管理 MQSeries Server 队列的 C# 控制台应用程序  
  
1.  创建一个新 Visual C# 控制台应用程序中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]同名**MQSeriesQueues**。  
  
2.  使用以下代码替换生成的 Program.cs 文件中的所有已有代码。  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using MQSAgentLib;  
  
    namespace MQSeriesQueues  
    {  
        class ManageQueues  
        {  
            public static void Main(string[] args)  
            {  
                // The first argument should be "c" (without quotes)  
                // to create a queue, anything else to delete a queue.  
                // The 2nd and 3rd arguments should be the name of   
                // the MQSeries Queue Manager and the name of   
                // the queue to be created or deleted for example  
                // the following usage will create the local   
                // queue testq for the Queue Manager QM_Test  
                // MQSeriesQueues c QM_Test testq  
                createordeleteQs(args[0], args[1], args[2]);  
            }  
  
            static void createordeleteQs(string Qswitch, string QMgr, string QName)  
            {   
            if ((Qswitch =="c" & (QMgr != null & QName != null)))  
                {  
                    CreateQueue(QMgr, QName);  
                }  
                else if(QMgr != null & QName != null)  
                {  
                    DeleteQueue(QMgr, QName);  
                }  
             }  
  
            static void CreateQueue(string Qmgr, string Qname)  
            {  
                MQSAdmin admin = new MQSAdmin();    
  
                ResultCode resultCode = admin.CreateQueue(Qmgr, Qname, 0, "", "", "", 0);  
  
                if ((resultCode & ResultCode.QueueCreated) == ResultCode.QueueCreated)  
                {  
                    Console.WriteLine("Queue Created.");  
                }  
                else if ((resultCode & ResultCode.QueueAlreadyExists) == ResultCode.QueueAlreadyExists)  
                {  
                    Console.WriteLine("Queue Already Exists.");  
                }  
            }  
  
            static void DeleteQueue(string Qmgr, string Qname)  
            {  
                MQSAdmin admin = new MQSAdmin();  
  
                ResultCode resultCode = admin.DeleteQueue(Qmgr, Qname);  
  
                if ((resultCode & ResultCode.QueueDeleted) == ResultCode.QueueDeleted)  
                {  
                    Console.WriteLine("Queue successfully deleted.");  
                }  
                if ((resultCode & ResultCode.QueueDoesNotExist) == ResultCode.QueueDoesNotExist)  
                {  
                    Console.WriteLine("Queue did not exist anyway!");  
                }  
            }  
  
        }  
    }  
    ```  
  
3.  添加对该项目的引用**MQSAgent 1.0 类型库**。 **MQSAgent 1.0 类型库**位于**COM**选项卡**添加引用**对话框。  
  
    > [!NOTE]
    >  运行此控制台应用程序的计算机中必须已经安装了 MQSAgent COM+ 组件。 有关安装 MQSAgent COM + 组件的详细信息请参阅[使用 MQSAgent COM + 配置向导](../core/using-the-mqsagent-com-configuration-wizard.md)。  
  
4.  生成控制台应用程序。  
  
5.  在编译的控制台应用程序所在的目录中打开一个命令提示窗口。  
  
6.  键入编译的控制台应用程序的名称和相应的参数，然后按 Enter。 例如，若要删除队列**testq**的队列管理器**QM_Test**在命令提示符下键入以下文本，并按 ENTER:  
  
    ```  
    MQSeriesQueues d QM_Test testq  
    ```  
  
7.  若要创建队列**testq**的队列管理器**QM_Test**在命令提示符下键入以下文本，并按 ENTER:  
  
    ```  
    MQSeriesQueues c QM_Test testq  
    ```