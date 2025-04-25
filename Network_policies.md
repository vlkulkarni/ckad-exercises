## Network Policies Exercises ##
**1 Question:**
  Write a Network Policy for the goodnamespace namespace that allows ingress traffic to the app:frontend pods only from pods that meet both of the following conditions:
  The pod must be labeled with role:api.
  The pod must be labeled with env:prod.
  Additionally, the policy should allow traffic only on TCP port 80.
**2 Question:**
  Create a Network Policy for goodnamespace that allows ingress traffic to the app:frontend pods from:
  Pods labeled with role:backend or
  Pods labeled with role:api.
  The policy should only allow traffic on TCP port 443.
**3 Question:**
  Write a Network Policy for the goodnamespace namespace that allows ingress traffic to the app:frontend pods from:
  Pods with label role:client in othernamespace and pods in the goodnamespace namespace with label role:service, or
  Pods with label role:api in the goodnamespace namespace.
  The policy should allow traffic only on TCP port 8080.
**4 Question:**
  Create a Network Policy for the goodnamespace namespace that allows ingress traffic to the app:frontend pods from:
  Pods in the backendnamespace labeled with role:frontend, and
  Pods in the goodnamespace labeled with role:api.
  The policy should allow traffic on TCP port 443.
**5 Question:**
  Write a Network Policy for the goodnamespace namespace that allows ingress traffic to the app:frontend pods from:
  Pods labeled with role:api in goodnamespace or
  Pods in the othernamespace with label app:service.
  The policy should allow traffic only on TCP port 80.
**6 Question:**
  Write a Network Policy for the goodnamespace namespace that allows ingress traffic to the app:frontend pods if the traffic is:
  From any pod labeled with role:api, and
  The source IP must be in the range 192.168.1.0/24.
  The policy should allow traffic only on TCP port 443.
