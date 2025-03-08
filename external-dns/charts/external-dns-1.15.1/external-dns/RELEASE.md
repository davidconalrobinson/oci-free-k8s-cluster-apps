### Added

- Added ability to configure `imagePullSecrets` via helm `global` value. ([#4667](https://github.com/kubernetes-sigs/external-dns/pull/4667)) _@jkroepke_
- Added options to configure `labelFilter` and `managedRecordTypes` via dedicated helm values. ([#4849](https://github.com/kubernetes-sigs/external-dns/pull/4849)) _@abaguas_

### Changed

- Allow templating `serviceaccount.annotations` keys and values, by rendering them using the `tpl` built-in function. ([#4958](https://github.com/kubernetes-sigs/external-dns/pull/4958)) _@fcrespofastly_
- Updated _ExternalDNS_ OCI image version to [v0.15.1](https://github.com/kubernetes-sigs/external-dns/releases/tag/v0.15.1). ([#5028](https://github.com/kubernetes-sigs/external-dns/pull/5028)) _@stevehipwell_

### Fixed

- Fixed automatic addition of pod selector labels to `affinity` and `topologySpreadConstraints` if not defined. ([#4666](https://github.com/kubernetes-sigs/external-dns/pull/4666)) _@pvickery-ParamountCommerce_
- Fixed missing Ingress permissions when using Istio sources. ([#4845](https://github.com/kubernetes-sigs/external-dns/pull/4845)) _@joekhoobyar_
