pipeline {
    agent any

    stages {
        stage('Deploy To Kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[
                    caCertificate: '''-----BEGIN CERTIFICATE-----
MIIDBTCCAe2gAwIBAgIISYR3wUDkAqEwDQYJKoZIhvcNAQELBQAwFTETMBEGA1UE
AxMKa3ViZXJuZXRlczAeFw0yNjA0MjEwNjQxMzZaFw0zNjA0MTgwNjQ2MzZaMBUx
EzARBgNVBAMTCmt1YmVybmV0ZXMwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEK
AoIBAQDlxgIxLhQOEpZbKUL8YBXD9xCIb9uV1ITeWbZyMS7tWAqW4BcofE6WjVF5
01WrsQyHukorbcvNKt8x3IZyk1Uea9mjaApv5JfhKSeB1IesHiniyNhefz0Mm9Vd
OyPa8/xCVHpNfMyu0zL0NmcHRfKLofiZKn1at0DeS+DmLIFRQMfDmmcqoz/5+8EQ
qvmkHGmxHhZqQqNTdlVWtenfM9R2kIxb64VgTeOQtcsz5Sk7Ksr9UbG33Y3TvSjc
d/XdJLbtL3hNjKaHvgebPgALEOHU4wYsaelFqgXEz61PDuFFWZJdB1wNjQiZQodH
RonU+8bbtDSpoBu47zlzI2YL/JH9AgMBAAGjWTBXMA4GA1UdDwEB/wQEAwICpDAP
BgNVHRMBAf8EBTADAQH/MB0GA1UdDgQWBBRdtr9/+fP0xrp0EqeUBZwomVoR3DAV
BgNVHREEDjAMggprdWJlcm5ldGVzMA0GCSqGSIb3DQEBCwUAA4IBAQC3mGLBbAEj
ma3rfbbdO6Z9adHh+BAXpEE3nJdVJGFsTKyYBZYf4KaoKE3DKXHhdbQmPqMP5t2t
S4rdSUe/EyBBf9VRWh169JJOt/TsQddffkygFlJXkm/x0bV9i+ZRldBg11GVuZly
q7zR3/quE3i4L3EKXHDjp/D2FyQmmJP6TiTSlYDyj4Jw/jU9/t3QrO2tgPTYfHm6
YKYcpJ6OLc6cRnynMFIQWHEhl05hrhxjSm5sB8kz0UErgdR4orPTKz1clpOxV33d
kt03XzgJNB1aebM6UWWmVufrvqeXvk3TInfCuA1BjnclikdDbv1qumMF0qGPz1LQ
uZNMTw2txgNF
-----END CERTIFICATE-----''',
                    clusterName: 'sydney-cluster-4',
                    contextName: '',
                    credentialsId: 'k8-token',
                    namespace: 'webapps',
                    serverUrl: 'https://6B2DFEDED4189B33DEB5DDE96F54FF12.gr7.ap-southeast-2.eks.amazonaws.com'
                ]]) {
                    sh "kubectl apply -f deployment-service.yml"
                }
            }
        }

        stage('Verify Deployment') {
            steps {
                withKubeCredentials(kubectlCredentials: [[
                    caCertificate: '''-----BEGIN CERTIFICATE-----
MIIDBTCCAe2gAwIBAgIISYR3wUDkAqEwDQYJKoZIhvcNAQELBQAwFTETMBEGA1UE
AxMKa3ViZXJuZXRlczAeFw0yNjA0MjEwNjQxMzZaFw0zNjA0MTgwNjQ2MzZaMBUx
EzARBgNVBAMTCmt1YmVybmV0ZXMwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEK
AoIBAQDlxgIxLhQOEpZbKUL8YBXD9xCIb9uV1ITeWbZyMS7tWAqW4BcofE6WjVF5
01WrsQyHukorbcvNKt8x3IZyk1Uea9mjaApv5JfhKSeB1IesHiniyNhefz0Mm9Vd
OyPa8/xCVHpNfMyu0zL0NmcHRfKLofiZKn1at0DeS+DmLIFRQMfDmmcqoz/5+8EQ
qvmkHGmxHhZqQqNTdlVWtenfM9R2kIxb64VgTeOQtcsz5Sk7Ksr9UbG33Y3TvSjc
d/XdJLbtL3hNjKaHvgebPgALEOHU4wYsaelFqgXEz61PDuFFWZJdB1wNjQiZQodH
RonU+8bbtDSpoBu47zlzI2YL/JH9AgMBAAGjWTBXMA4GA1UdDwEB/wQEAwICpDAP
BgNVHRMBAf8EBTADAQH/MB0GA1UdDgQWBBRdtr9/+fP0xrp0EqeUBZwomVoR3DAV
BgNVHREEDjAMggprdWJlcm5ldGVzMA0GCSqGSIb3DQEBCwUAA4IBAQC3mGLBbAEj
ma3rfbbdO6Z9adHh+BAXpEE3nJdVJGFsTKyYBZYf4KaoKE3DKXHhdbQmPqMP5t2t
S4rdSUe/EyBBf9VRWh169JJOt/TsQddffkygFlJXkm/x0bV9i+ZRldBg11GVuZly
q7zR3/quE3i4L3EKXHDjp/D2FyQmmJP6TiTSlYDyj4Jw/jU9/t3QrO2tgPTYfHm6
YKYcpJ6OLc6cRnynMFIQWHEhl05hrhxjSm5sB8kz0UErgdR4orPTKz1clpOxV33d
kt03XzgJNB1aebM6UWWmVufrvqeXvk3TInfCuA1BjnclikdDbv1qumMF0qGPz1LQ
uZNMTw2txgNF
-----END CERTIFICATE-----''',
                    clusterName: 'sydney-cluster-4',
                    contextName: '',
                    credentialsId: 'k8-token',
                    namespace: 'webapps',
                    serverUrl: 'https://6B2DFEDED4189B33DEB5DDE96F54FF12.gr7.ap-southeast-2.eks.amazonaws.com'
                ]]) {
                    sh "kubectl get svc -n webapps"
                }
            }
        }
    }
}
