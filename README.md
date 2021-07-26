1. Initial am configurat aws cli(access key, secret access key, regiune).
2. Am creat fisierul templatenitavalentin.yaml .
3. Am folosit comanda aws cloudformation deploy --template-file templatenitavalentin.yml --stack-name valentin-nita, pentru a urca fisierul yaml.
4. Am creat un mic folder html vn-site.html, pe care ulterior l-am uploadat in s3 bucket.
5. Am refolosit comanda aws cloudformation deploy --template-file templatenitavalentin.yml --stack-name valentin-nita pt a adauga output-ul in fisierul yaml :
6. Outputs:
  WebsiteURL:
    Value: !GetAtt 
      - S3Bucket
      - WebsiteURL
    Description: URL for website hosted on S3
  S3BucketSecureURL:
    Value: !Join 
      - ''
      - - 'https://'
        - !GetAtt 
          - S3Bucket
          - DomainName
    Description: Name of S3 bucket to hold website content
 7. Am verificat in consola daca totul a fost updatat iar ca ultim pas am pus bifa la Read la tabul Permissions pentru public access.
