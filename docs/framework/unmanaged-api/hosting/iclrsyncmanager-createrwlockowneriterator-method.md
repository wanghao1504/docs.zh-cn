---
title: "ICLRSyncManager::CreateRWLockOwnerIterator 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRSyncManager.CreateRWLockOwnerIterator
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRSyncManager::CreateRWLockOwnerIterator
helpviewer_keywords:
- ICLRSyncManager::CreateRWLockOwnerIterator method [.NET Framework hosting]
- CreateRWLockOwnerIterator method [.NET Framework hosting]
ms.assetid: b5535b87-9439-424e-b9b3-7d6fafb9819e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1f153550544a8e7622ea3cec0273ff9a97a99f91
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrsyncmanagercreaterwlockowneriterator-method"></a><span data-ttu-id="ec41d-102">ICLRSyncManager::CreateRWLockOwnerIterator 方法</span><span class="sxs-lookup"><span data-stu-id="ec41d-102">ICLRSyncManager::CreateRWLockOwnerIterator Method</span></span>
<span data-ttu-id="ec41d-103">公共语言运行时 (CLR) 创建主机可用于确定的读取器 / 编写器锁等待的任务集的迭代器的请求。</span><span class="sxs-lookup"><span data-stu-id="ec41d-103">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec41d-104">语法</span><span class="sxs-lookup"><span data-stu-id="ec41d-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockOwnerIterator (  
    [in]  SIZE_T    cookie,  
    [out] SIZE_T   *pIterator  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ec41d-105">参数</span><span class="sxs-lookup"><span data-stu-id="ec41d-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="ec41d-106">[in]与所需的读取器 / 编写器锁定关联的 cookie。</span><span class="sxs-lookup"><span data-stu-id="ec41d-106">[in] The cookie associated with the desired reader-writer lock.</span></span>  
  
 `pIterator`  
 <span data-ttu-id="ec41d-107">[out]指向一个迭代器，可以传递给[GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md)和[DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ec41d-107">[out] A pointer to an iterator that can be passed to the [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) and [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec41d-108">返回值</span><span class="sxs-lookup"><span data-stu-id="ec41d-108">Return Value</span></span>  
  
|<span data-ttu-id="ec41d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ec41d-109">HRESULT</span></span>|<span data-ttu-id="ec41d-110">描述</span><span class="sxs-lookup"><span data-stu-id="ec41d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ec41d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ec41d-111">S_OK</span></span>|<span data-ttu-id="ec41d-112">`CreateRWLockOwnerIterator`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="ec41d-112">`CreateRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="ec41d-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ec41d-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ec41d-114">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="ec41d-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ec41d-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ec41d-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ec41d-116">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="ec41d-116">The call timed out.</span></span>|  
|<span data-ttu-id="ec41d-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ec41d-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ec41d-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="ec41d-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ec41d-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ec41d-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ec41d-120">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="ec41d-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ec41d-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ec41d-121">E_FAIL</span></span>|<span data-ttu-id="ec41d-122">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="ec41d-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ec41d-123">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="ec41d-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ec41d-124">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="ec41d-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ec41d-125">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="ec41d-125">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="ec41d-126">`CreateRWLockOwnerIterator`当前正在运行托管的代码的线程上调用。</span><span class="sxs-lookup"><span data-stu-id="ec41d-126">`CreateRWLockOwnerIterator` was called on a thread that is currently running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec41d-127">备注</span><span class="sxs-lookup"><span data-stu-id="ec41d-127">Remarks</span></span>  
 <span data-ttu-id="ec41d-128">主机通常调用`CreateRWLockOwnerIterator`， `DeleteRWLockOwnerIterator`，和`GetRWLockOwnerNext`死锁检测期间的方法。</span><span class="sxs-lookup"><span data-stu-id="ec41d-128">Hosts typically call the `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, and `GetRWLockOwnerNext` methods during deadlock detection.</span></span> <span data-ttu-id="ec41d-129">主机负责确保读取器 / 编写器锁仍然有效，因为 CLR 使不尝试使读取器 / 编写器锁处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="ec41d-129">The host is responsible for ensuring that the reader-writer lock is still valid, because the CLR makes no attempt to keep the reader-writer lock alive.</span></span> <span data-ttu-id="ec41d-130">多个策略是可用于主机以确保有效性的锁：</span><span class="sxs-lookup"><span data-stu-id="ec41d-130">Several strategies are available for the host to ensure the validity of the lock:</span></span>  
  
-   <span data-ttu-id="ec41d-131">主机可以阻止读取器 / 编写器锁释放调用 (例如， [ihostsemaphore:: Releasesemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)) 同时确保此块不会导致死锁。</span><span class="sxs-lookup"><span data-stu-id="ec41d-131">The host can block release calls on the reader-writer lock (for example, [IHostSemaphore::ReleaseSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)) while ensuring that this block does not cause deadlock.</span></span>  
  
-   <span data-ttu-id="ec41d-132">主机可以阻止从正在等待读取器 / 编写器锁，与关联的事件对象退出同样可以确保此块不会导致死锁。</span><span class="sxs-lookup"><span data-stu-id="ec41d-132">The host can block the exit from waiting on the event object associated with the reader-writer lock, again ensuring that this block does not cause deadlock.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec41d-133">`CreateRWLockOwnerIterator`必须仅在当前正在执行非托管的代码的线程上调用。</span><span class="sxs-lookup"><span data-stu-id="ec41d-133">`CreateRWLockOwnerIterator` must be called only on threads that are currently executing unmanaged code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec41d-134">要求</span><span class="sxs-lookup"><span data-stu-id="ec41d-134">Requirements</span></span>  
 <span data-ttu-id="ec41d-135">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ec41d-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec41d-136">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ec41d-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ec41d-137">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ec41d-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ec41d-138">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec41d-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec41d-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec41d-139">See Also</span></span>  
 [<span data-ttu-id="ec41d-140">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="ec41d-140">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="ec41d-141">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="ec41d-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)