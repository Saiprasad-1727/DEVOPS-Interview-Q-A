## 15. **Difference between Statefulset and Deployment ? 
- **Deployment**: Manages stateless applications, ensuring a specified number of pod replicas are running.
- **statefulset**: manages stateful applications, providing guarantees about the ordering and uniqueness of pods.

* For example, a web server would use a Deployment, while a database that requires
Stable storage would use Statefulset.
