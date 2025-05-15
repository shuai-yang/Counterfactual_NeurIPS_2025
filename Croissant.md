{
  "@context": {
    "@language": "en",
    "@vocab": "https://schema.org/",
    "arrayShape": "cr:arrayShape",
    "citeAs": "cr:citeAs",
    "column": "cr:column",
    "conformsTo": "dct:conformsTo",
    "cr": "http://mlcommons.org/croissant/",
    "data": {
      "@id": "cr:data",
      "@type": "@json"
    },
    "dataBiases": "cr:dataBiases",
    "dataCollection": "cr:dataCollection",
    "dataType": {
      "@id": "cr:dataType",
      "@type": "@vocab"
    },
    "dct": "http://purl.org/dc/terms/",
    "extract": "cr:extract",
    "field": "cr:field",
    "fileProperty": "cr:fileProperty",
    "fileObject": "cr:fileObject",
    "fileSet": "cr:fileSet",
    "format": "cr:format",
    "includes": "cr:includes",
    "isArray": "cr:isArray",
    "isLiveDataset": "cr:isLiveDataset",
    "jsonPath": "cr:jsonPath",
    "key": "cr:key",
    "md5": "cr:md5",
    "parentField": "cr:parentField",
    "path": "cr:path",
    "personalSensitiveInformation": "cr:personalSensitiveInformation",
    "recordSet": "cr:recordSet",
    "references": "cr:references",
    "regex": "cr:regex",
    "repeated": "cr:repeated",
    "replace": "cr:replace",
    "sc": "https://schema.org/",
    "separator": "cr:separator",
    "source": "cr:source",
    "subField": "cr:subField",
    "transform": "cr:transform"
  },
  "@type": "sc:Dataset",
  "distribution": [
    {
      "@type": "cr:FileObject",
      "@id": "repo",
      "name": "repo",
      "description": "The Hugging Face git repository.",
      "contentUrl": "https://huggingface.co/datasets/zhonghuajia2025/counterfactual/tree/refs%2Fconvert%2Fparquet",
      "encodingFormat": "git+https",
      "sha256": "https://github.com/mlcommons/croissant/issues/80"
    },
    {
      "@type": "cr:FileSet",
      "@id": "parquet-files-for-config-default",
      "containedIn": {
        "@id": "repo"
      },
      "encodingFormat": "application/x-parquet",
      "includes": "default/*/*.parquet"
    }
  ],
  "recordSet": [
    {
      "@type": "cr:RecordSet",
      "dataType": "cr:Split",
      "key": {
        "@id": "default_splits/split_name"
      },
      "@id": "default_splits",
      "name": "default_splits",
      "description": "Splits for the default config.",
      "field": [
        {
          "@type": "cr:Field",
          "@id": "default_splits/split_name",
          "dataType": "sc:Text"
        }
      ],
      "data": [
        {
          "default_splits/split_name": "validation"
        }
      ]
    },
    {
      "@type": "cr:RecordSet",
      "@id": "default",
      "description": "zhonghuajia2025/counterfactual - 'default' subset",
      "field": [
        {
          "@type": "cr:Field",
          "@id": "default/split",
          "dataType": "sc:Text",
          "source": {
            "fileSet": {
              "@id": "parquet-files-for-config-default"
            },
            "extract": {
              "fileProperty": "fullpath"
            },
            "transform": {
              "regex": "default/(?:partial-)?(validation)/.+parquet$"
            }
          },
          "references": {
            "field": {
              "@id": "default_splits/split_name"
            }
          }
        },
        {
          "@type": "cr:Field",
          "@id": "default/image",
          "dataType": "sc:ImageObject",
          "source": {
            "fileSet": {
              "@id": "parquet-files-for-config-default"
            },
            "extract": {
              "column": "image"
            },
            "transform": {
              "jsonPath": "bytes"
            }
          }
        }
      ]
    }
  ],
  "conformsTo": "http://mlcommons.org/croissant/1.1",
  "name": "counterfactual",
  "description": "\n\t\n\t\t\n\t\tOn the Eligibility of LLMs for Counterfactual Reasoning: A Decompositional Study\n\t\n\n\n\t\n\t\t\n\t\t⚠️ IMPORTANT\n\t\n\nThis repository is anonymous and is solely intended for review purposes. \n\n\t\n\t\t\n\t\t💡 Introduction\n\t\n\nThis repository contains the code and resources for our research on counterfactual reasoning in Large Language Models (LLMs). We introduce a systematic framework that includes standardized processes for counterfactual generation, evaluation, and interpretation across multiple… See the full description on the dataset page: https://huggingface.co/datasets/zhonghuajia2025/counterfactual.",
  "alternateName": [
    "zhonghuajia2025/counterfactual"
  ],
  "creator": {
    "@type": "Person",
    "name": "Shuai Yang",
    "url": "https://huggingface.co/zhonghuajia2025"
  },
  "keywords": [
    "apache-2.0",
    "1K - 10K",
    "imagefolder",
    "Image",
    "Datasets",
    "Croissant",
    "🇺🇸 Region: US"
  ],
  "license": "https://choosealicense.com/licenses/apache-2.0/",
  "url": "https://huggingface.co/datasets/zhonghuajia2025/counterfactual"
}
